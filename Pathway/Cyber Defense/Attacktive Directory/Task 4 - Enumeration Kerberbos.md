Installing Kerbrute

Go to the https://github.com/ropnop/kerbrute/releases, and select the binary version that works with your system. I'm running on the virtual box provided by THM, so I selected kerbrute_linux_386. 
Once downloaded, you'll need to change the download to an executable. 
```
chmod +x kerbrute_linux_386
```

Next, you will need to download the Username and password files provided in the tasks. 
```
wget https://raw.githubusercontent.com/Sq00ky/attacktive-directory-tools/master/userlist.txt
wget https://raw.githubusercontent.com/Sq00ky/attacktive-directory-tools/master/passwordlist.txt

```

Now, we can use Kerbrute and username files to enumerate user information on the Domain Controller. 
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/2e472309-dffe-4f8e-9ac2-0c804be22a22)


Question:
What command within kerbrute will allow us to enumerate valid usernames?

Answer: svc-admin


Question:
What notable account is discovered?
Review the user enumeration above for the answer.
Answer: svc-admin

Question:
What is the other notable account discovered?
Review the user enumeration above for the answer.
Answer: backup
