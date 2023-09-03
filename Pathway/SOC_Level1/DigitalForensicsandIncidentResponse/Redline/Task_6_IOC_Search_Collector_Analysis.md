<h2>**Scenario:**</h2>
You are assigned to do a threat-hunting task at Osinski Inc. They believe there has been an intrusion, and the malicious actor was using the tool to perform the lateral movement attack, possibly a "pass-the-hash" attack.

**Task:** Can you find the file planted on the victim's computer using IOC Editor and Redline IOC Search Collector? 

So far, you only know the following artifacts for the file: 

File Strings: 
- 20210513173819Z0w0=
- <?<L<T<g=
  
File Size (Bytes): 
- 834936

<h2>Setup</h2>
Create IOC 
Start IOC, Make a new file folder, and Make a new Indicator; 

**Indicator Parameters
- Name: Pass-The-Hash
- Author: Shawn
- Description: Looks for lateraling movement, where the threat actor is utilizing pass-the-hash
- OR (Statement)
  - Item: File String contains 20210513173819Z0w0=
  - Item: File String contains <?<L<T<g=
  - Item: File Size is 834936
    
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/f39be984-4d0f-4c71-b663-9ea2cbd78131)


Save IOC



<h2>Analayis report with IOC</h2>
- Open Redline
- Select IOC reports
- Create a New IOC report
- Load the recently created IOC folder, and select Indicator

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/2cf4665b-9c1e-4a6c-95df-ff4367c28752)


<h2>View Report</h2>

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/b7602186-2eaf-4f8b-a688-513dbbc2ac49)


<H2>Answers</H2>

Questions 1-5: Can be found in the report window.


Question 6: The hint suggests converting the file with Powershell; the file doesn't exist on the computer. As an alternative, you go to [Virustotal](https://www.virustotal.com/gui/home/upload)
and enter the MD5 hash to look up more details about the virus. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/70dc4a23-d175-480f-986f-c157340f37d8)

Click on details to find the SHA256 hash.

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/729d0bef-79ee-4e53-b3bd-9f21e3fbb8af)

Question 7:  The real file name can be found furth below on this page.  

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/9de0c314-d5a8-4815-9889-72d2c526184b)

