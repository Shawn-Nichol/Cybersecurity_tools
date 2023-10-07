Question: 
A Federal law enforcement agency reports that Taedonggang often spear phishes its victims with zip files that have to be opened with a password. What is the name of the attachment sent to Frothly by a malicious Taedonggang actor?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/2ad0119a-c9d7-445a-8b07-9c13eeff7e51)

Use the interesting field to identify the attachment file name.

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/855d8f18-0e8d-43c0-8d30-81288216db26)


Answer: Invoice.zip


Question: 
What is the password to open the zip file?

Do a control F in the raw data and type "Password."

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/e24b3c36-6f31-4634-a71f-7d804eaa2da3)


Answer: 912345678

Question: 
The Taedonggang APT group encrypts most of its traffic with SSL. What is the "SSL Issuer" that they use for the majority of their traffic? Answer guidance: Copy the field exactly, including spaces.

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/45158615-502c-40b6-9f03-8469096c2cd5)

Look under interesting fields and select SSL issuer; all entries start with "C = US"
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/28f389ac-8003-4ab7-8e42-6efcb02e433d)


Answer: C = US

Question:
What unusual file does winsys32.dll cause to be downloaded into the Frothly environment?

Answer:

Question:
What is the first and last name of the poor innocent sap who was implicated in the metadata of the file that executed PowerShell Empire on the victim's workstation? 

Answer:


Question:
Within the document, what kind of points are mentioned if you found the text? 

Answer:

Question: 
To maintain persistence in the Frothly network, Taedonggang APT configured several Scheduled Tasks to beacon back to their C2 server. What single webpage is most contacted by these Scheduled Tasks? Answer example: index.php or images.html

Answer:
