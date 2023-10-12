Rubeus is a powerful tool for attacking Kerberos.

Rebeus has various attacks and features that make it a very versatile tool for attacking Kerberos. Some tools and attacks include overpassing the hash, ticket requests and renewals, ticket management, ticket extraction, harvesting pass the ticket, AS-REP Roasting, and kerberoasting. 

https://github.com/GhostPack/Rubeus

Harvesting Tickets w/ Rebeus
Gather tickets that are being transferred to the KDC and save them for use in other attacks, such as the pass-the-ticket attack. 


# Rubues Harvesting
First, RDP into the remote server, Start Remmina in the terminal, and enter the credentials.
```
remmina

RDP: 10.10.211.14
User: Administrator
Password: P@$$W0rd
Domain: Controller.local
```

Navigate to the download directory so you can access Rubeus. </br>
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/32c9bab3-b91f-4e6d-84c2-8131fc37852a)

Run the Rubeus harvest.

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/94a35fa9-93d9-4ed5-a9c0-e6428a674716)

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/7925b634-ba8d-4845-8736-2db5aad8a24c)


# Rubues Brute force
Run the following command to add CONTROLLER.local to the host file
```
echo 10.10.211.14 CONTROLLER.local >> C:\Windows\System32\drivers\etc\hosts
```
You can verify this works by pinging the CONTROLLER.local, and it should return the IP address used in the command. 

Run Brute force Rubues

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/e0645768-6e11-42cc-baaf-f4c7ddec7da6)

Question:
Which Domain  admin do we get a ticket for when harvesting Tickets?
Check the screenshot in the harvesting section.
Answer: Administrator

Question:
Which domain controller do we get a ticket for when harvesting tickets?
Check the screenshot in the harvesting section.
Answer: CONTROLLER-1

