Kerbrute is a popular enumeration tool used to brute-force and enumerate valid AD users by abusing Kerberos pre-authentication.

By brute-forcing kerberos p-re-authentication, you do not trigger the account failed to log on to the event, which can throw up red flags to blue teams. When brute-forcing through Kerberos, you can brute-force by only sending a single UDP frame to the KDC, allowing you to enumerate the users on the domain from a wordlist. 

Kerbrute install
1) Download a precompile binary for your OS https://github.com/ropnop/kerbrute/releases
2) Rename Kerbrute_linux_amd64 to kerbrute
3) chmod +x Kerbrute to make kerbrute executable.


You need to add the DNS domain name along with the machine IP to /etc/hosts inside of your attacker machine, or these attacks will not work for you - 10.10.244.67  CONTROLLER.local   

```
sudo nano /etc/hosts
```

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/61acbdcc-d74e-4fdc-b161-457b2b34dbc1)


Run Kerbrute to obtain all the information you need for the questions. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/a847b96f-7096-4be2-9a29-c5299ee36943)


Question:
How many total users do we enumerate?

Answer: 10

Question
What is the SQL service account name?

Answer: sqlservice

Question
What is the second machine account name?

Answer: machine2

Question
What is the third user account name?

Answer: User 3
