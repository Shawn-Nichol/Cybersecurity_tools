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

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/bc92ccde-a882-481a-97ce-7e9cd11e6ed0)

Follow the instructions in the hint to copy the text from SPLUNK to the THM answer properly. 

Answer: 나는_데이비드를_사랑한다.hwp

Question:
What is the first and last name of the poor innocent sap who was implicated in the metadata of the file that executed PowerShell Empire on the victim's workstation? 

Use the Hybrid Analysis link provided in the task and navigate around to find out details about the file. 
Hybrid Analysis - https://www.hybrid-analysis.com/sample/d8834aaa5ad6d8ee5ae71e042aca5cab960e73a6827e45339620359633608cf1/598155a67ca3e1449f281ac4
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/ee18c170-8dfa-44fc-835c-a9232e9843b3)


Answer: Ryan Kovar


Question:
Within the document, what kind of points are mentioned if you found the text? 

Use the AnyRun link provided in the task; it will open the virus and provide you with the answer.
Any.run - https://app.any.run/tasks/15d17cd6-0eb6-4f52-968d-0f897fd6c3b3

Answer: cybereastegg

Question: 
To maintain persistence in the Frothly network, Taedonggang APT configured several Scheduled Tasks to beacon back to their C2 server. What single webpage is most contacted by these Scheduled Tasks? Answer example: index.php or images.html

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/15da5726-cbdc-49da-bb31-86e84be08ded)

Answer:
