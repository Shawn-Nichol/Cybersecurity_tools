## Question: What is the version and year of the Windows machine?

Answer: Windows Server 2016



## Question: Which user logged in last?

Answer: Administrator



## Question: When did John log onto the system last?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/57b11d81-3f88-4ee3-afef-788b2e8478da)

Answer: 03/02/2019 5:48:32 PM



## Quesiton: What IP does the system connect to when it first starts?

Regedit
computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run

Answer: 10.34.2.3



## Question: What two accounts had administrative privileges

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/ff07958d-4aae-4941-a1d4-e649dffc27dc)

Answer: Jenny, Guest



## Question: What the name of the scheduled task that is malicious?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/5a0c02b1-e937-4193-bc23-06d30cd5bc73)

Answer: Clean file system



## Question: What file was the task trying to run daily?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/99cdfaec-635a-4a7e-9356-0c175c10be22)

Answer: nc.ps1



## Question: What port did the file listen locally for?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/99cdfaec-635a-4a7e-9356-0c175c10be22)

Answer: 1348



## Question: When did Jenny last Logon?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/67e37dcb-c8b2-462b-b407-5919e2f77ee3)

Answer: Never



##Question: At what date did the compromise take place?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/965103a3-f21f-4456-bb46-b3b30bea22a4)

Answer: 03/02/2019



## Question: During the compromise, at what time did Windows first assign special privileges to a new logon?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/125a9261-879c-4493-a071-bc96c58f4a22)

Answer: 03/02/2019 4:04:49 PM



## Question: What tool was used to get Windows passwords?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/72fd7b8e-3af1-4e6c-8df3-b887b88221ef)

Answer: Mimikatz



## Question: What was the attacker's external control and command server IP?

Access the Hosts file and review the IP addresses and web addresses. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/5de74d3e-6070-4ad4-b237-9bc64820a2f0)


The host file contains the DNS records of recently visited sites. The Google IP address doesn't look right; verify if this address belongs to Google. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/9172a4bd-0946-4aa8-aa1f-b11763fd90f5)

Answer: 76.32.97.132



## Question: What was the extension name of the shell uploaded via the server's website?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/bfa17440-59b3-4b2e-9be2-39528a82d1a5)


## Question: What was the last port the attacker opened?

View the firewall rules, and you can identify this is the first rule; you can tell by looking up what the port number is used for. 

Answer: 1337



## Question: Check for DNS poisoning; what site was targeted?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/9172a4bd-0946-4aa8-aa1f-b11763fd90f5)

Answer: Google.com

