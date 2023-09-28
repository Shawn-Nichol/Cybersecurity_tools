## Task 7 Authentication Methods
All credentials are stored in the DC. Whenever a user tries to authenticate to a service using domain credentials, the service will need to ask the DC to verify if they are correct. Two protocols can be used for network authentication in Windows domains.

- Kerbos: Used by any recent versions of Windows. This is the default protocol in any recent domain.
- NetNTLM: Legacy authentication protocol kept for compatibility purposes.

Kerbos
Step 1
The user sends their username and a timestamp encrypted using a key derived from their password to the Key Distribution Center (KDC), a service usually installed on the DC in charge of creating Kerberos tickets on the network. 

The KDC will create and send back a Ticket Granting Ticket (TGT), which will allow the user to request additional tickets to access specific services. The need for a ticket to get more tickets may sound a bit weird, but it allows users to request service tickets without passing their credentials every time they want to connect to a service. Along with the TGT, a Session Key is given to the user, which they will need to generate the following request.
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/ef19fa89-45a6-4106-908a-4a204aee3da3)

Step 2
When a user wants to connect to a service on the network, like a share, website, or database, they will use their TGT to ask the KDC for a Ticket Granting Service (TGS). TGS are tickets that allow connection to specific services they were created for. To request a TGS, the user will send their username and a timestamp encrypted using the Session Key, along with the TGT and a Service Principal Name (SPN), which indicates the service and server name we intend to access.

As a result, the KDC will send us a TGS along with a Service Session Key, which we will need to authenticate to the service we want to access. The TGS is encrypted using a key derived from the Service OWner Hash. The service OWner is the user or machine account that the service runs under. THE TGS contains a copy of the service Session Key on its encrypted contents so that the service Owwner can access it by decrypting the TGS

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/cb5c7f7f-ef16-4c29-ad1e-2d8d36058be8)

Step 3 
The TGS  can then be sent to the desired service to authenticate and establish a connection. The service  will use its configured account's password hash to decrypt the TGS and validate the SAervice Session key. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/e01b3eb1-cc0e-48c0-a79b-44946780816a)


NetNTLM Authentication

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/92b67752-0173-45e3-a15b-73e435017b68)

1. The client sends an authentication request to the server they want to access.
2. The server generates a random number and sends it as a challenge to the client.
3. The client combines their NTLM password hash with the challenge to generate a response to the challenge and sends it back to the server for verification.
4. The server forwards the challenge and the response to the DC for verification
5. The domain controller uses the challenge to recalculate the response and compares it to the original response sent by the client. If they both match, the client is authenticated; otherwise, access is denied. The authentication result is sent back to the server.
6. The server forwards the authentication result to the client.


Question:: Will the current version of Windows use NetNTLM as the preferred authentication protocol by default
Answer: nay

Question: When referring to Kerberos, what type of ticket allows us to request further tickets known as TGS?
Answer: Ticket Granting Ticket

Question: When using NetwNTLM, is a user's password transmitted  over the network at any point?
Answer: nay
