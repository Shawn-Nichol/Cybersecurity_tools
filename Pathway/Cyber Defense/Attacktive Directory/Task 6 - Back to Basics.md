Question
What utility can we use to map remote SMB sahres?

Answer: smbclient

Question
Which option will list shares?

Use man smbClient for details. 

Answer: -L

Question
How many remote shares is the server listing?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/d0a8f16b-f7f5-45d0-b467-2fb1a214e2f8)

Answer: 6

Question: 
There is one particular share that we have access to that contains a text file. Which share is it?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/4550c091-290b-4a9a-9ac2-0de9adf63c97)

Answer:backup

Question:
What is the content of the file?
List the files and copy the files you are interested back to you computer. 
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/577ccfbf-ceb2-4ca1-9b99-29f3ac0b8f41)

Open copied file
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/bf6e8d58-1f43-4615-9a48-cb5a5fb2e936)


Answer: YmFja3VwQHNwb29reXNlYy5sb2NhbDpiYWNrdXAyNTE3ODYw


Question
Decoding the contents of the file, what is the full contents? 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/3f1a230a-4ed7-489f-b135-c71f679ec4f3)

Answer: backup@spookysec.local:backup2517860r


