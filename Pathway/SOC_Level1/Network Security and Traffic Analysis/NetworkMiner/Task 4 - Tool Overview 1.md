## Landing page

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/9dc4b7df-7a4c-4825-a7be-a28e08d43846)


## Case panel
The case panel shows the list of the investigated pcap files. 


![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/05f43ac6-bf7c-4f4c-a811-ad0a57af5c5f)

## Hosts
The host menu shows the identified hosts in the pcap file. This section provides information on
- IP address
- MAC address
- OS type
- Open ports
- Sent/Received packets
- Incoming/Outgoing sessions
- Host details

OS fingerprinting uses the satori Github repo and p0f, and the MAC address database uses the mac-ages GitHub repo.


![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/61bb288b-aad4-4ecc-9225-05fa056ec2b9)


## Session
The session menu shows the detected session in the pcap file. This section provides information on
- File number
- Client and server address
- Source and destination port
- Protocol
- Start time


## Credentails
The credentials menu shows extracted credentials and password hashes from investigated pcaps. You can use Hashcat and John the Ripper to decrypt extra credentials. Network Miner can extract credentials, including. 
- Kerbos Hashes
- NTLM Hashes
- RDP cookies
- HTTP cookies
- HTTP requests
- IMAP
- FTP
- SMTP
- MS SQL

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/3270b8db-4a80-47a5-9ee8-d23ca38e76ee)

Question: What is the total number of frames? 
Answer: 460

Question How many IP addresses use the same MAC address with host 145.253.2.203?
Answer: 2

Question: How many packets were sent from host 65.208.228.223?
Answer: 72

Question: What is the name of the webserver banner under host 65.208.228.223?
Answer: Apache

Question what is the extracted username?
Answer: #B\Administrator

Question: What is the extracted password?
Answer: $NETNTLMv2$#B$136B077D942D9A63$FBFF3C253926907AAAAD670A9037F2A5$01010000000000000094D71AE38CD60170A8D571127AE49E00000000020004003300420001001E003000310035003600360053002D00570049004E00310036002D004900520004001E0074006800720065006500620065006500730063006F002E0063006F006D0003003E003000310035003600360073002D00770069006E00310036002D00690072002E0074006800720065006500620065006500730063006F002E0063006F006D0005001E0074006800720065006500620065006500730063006F002E0063006F006D00070008000094D71AE38CD601060004000200000008003000300000000000000000000000003000009050B30CECBEBD73F501D6A2B88286851A6E84DDFAE1211D512A6A5A72594D340A001000000000000000000000000000000000000900220063006900660073002F003100370032002E00310036002E00360036002E0033003600000000000000000000000000


