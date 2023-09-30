Task 1 
## About the Vulnerability
Zero logons is a purely statistics-based attack that abuses a feature within MS-NRPC (Microsoft Netlogon  Remote Protocol); MS-NRPC is a critical authentication component of Active Directory that handles authentication for user and machine accounts. In short, the attack mainly focuses on a poor implementation of Cryptography. To be more specific, Microsoft chose to use AES-CFB8 for a function called ComputeNetlogonCredential, which is normally fine, except they had hard-coded the initialization vector to use all zeros instead of a random string. When an attack sends a message only containing zeros with the IV of zero, there is a 1-in-256 chance that the cipher text will be zero. 

## About Machine Accounts
Normally, if we tried a statistics-based attack on any user account, we would get locked out. This is not the case if we apply this principle to machine accounts. Machine accounts behave in a much different way than standard user accounts. They have no predefined account lockout attempts because a 64+ character alphanumeric password is normally used to secure them, making them very difficult to break into. They're

## Abusing the Vulnerability
Machine accounts often hold system-level privileges, which we can use for a variety of things. If you're not familiar with AD, we can take the DC machine account and attempt to use the granted authentication in conjunction with secretsdump.py (SecretsDump is a password-dumping utility like Mimikatz, except it lives on the network instead of the host) to dump all of the passwords within the domain. At this point, we have a rough kill chain starting to form.

Use Zero Logon to bypass authentication on the DC machine account -> Run secaretsdump.py to dump credentials -> Crack/passDomain Admin hashes -> ??? -> Profit.

## Analyzing the MS-NRPC Logon Process
At this point, we know a vulnerability exists, but we're not quite sure how to exploit it yet. We'll be covering that soon, but what we do know is there's a vulnerability within the way MS handles Authentication within ComputerNetLogonCredetial function of MS-NRPC. To better understand the vulnerability, we need to do a bit of a deeper dive into how MS handles authentication to NRPC.

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/2900fc43-1bd2-410a-a53b-6b88287466bf)

** Step 1** The client creates a NetrServerReqChallenge and send it off. This contains the following values. 
1. The DC
2. The target Device
3. A Nonce (in our case, 16 Bytes of Zero).

** Step 2** The server receives the NetrServerReqChallenge, the server will then generate it's own Nonce (this is called the Server Challenge), the server will send the serverr challenge back

** Step 3** The client will compute it's NetLogon Credentials with the Server Challenge Provided. It uses the NetrServerAuthenticat3 method which requires the following parameters.

1. A Custom Binding handle (Impaacket handles this for us, it's negotiated prior).
2. An account Name (The DC machine account name)
3. A secure channel Type (Impacket sort of handles this for us, but we still need to specify it: [nrpc.NETLOGON_SECURE_CHANNEL_TYPE.ServerSecureChannel])
4. The Computer Name (The DC ex: DC01)
5. The Client Credential String (This will be 8 hextets of \x00 [16 Bytes of Zero])
6. Negotiation Flags(The following value observed from a Win10 client with sign/seal flags disabled: 0x212fffff Provided by secure)

** Step 4**
The server will receive the NetrServerAutheticate request and will compute the same request itself using it's known good values. If the results are good, the server will send the required info back to the  client. 

At this point, the attempt to exploit the Zero Logon vulnerability is underway. The above steps will be looped through a certain number of times to computations as the client. This is where our 1-in-256 chance comes. 

** Step 5 **
If the server calculates the same value, the client will re-verify, and once mutual agreement is confirmed, they will agree on a session key. The session key will encrypt communication between the client and the server, which means authentication is successful. 

## Impact Installation
As a prior warning, Impacket can be quite fussy when it comes to some modules within nrpc.py; because of this, we recommend using the TryHackMe attack box. 


## Task 3 - The Proof of Concept
Question: What method will allow us to change Passwords over NRPC?
Answer: NetrServerPasswordSet2

Question: What are the required fields for the method per the MS document?
Answer: PrimaryName, AccountName, SecureChannelType, ComputerName, Authenticator, ReturnAuthenticator, ClearNewPassword

Question: What Opnumber is the method?
Answer: 30

Task 4 Lab it up


Enumeration
Run nmap scan to get information on the server.
```
nmap -sV -sC #.#.#.# 
```


Question: What is the NetBios name of the DC? </br>

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/a947b8da-4c29-466d-a7df-5bbf38a16be6)

Answer: DC01

Question: What is the NetBIOS domain name of the network? </br>

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/3c128957-16be-4612-bb4f-87d48d71ccf1)

Answer: HoloLive

Question What domain are you attacking?
Answer: HoloLive.local

Question: What is the Local Administrator's NTLM hash?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/e772dff4-fe16-41f3-ac6a-ac556df616eb)


Answer: 3f3ef89114fb063e3d7fc23c20f65568

Question: How Many Domain Admin Accounts are there? </br>

Answer: 2

Question: What is the root flag?
Answer: THM{Zer0Log0nDa4rkTh1rty}


