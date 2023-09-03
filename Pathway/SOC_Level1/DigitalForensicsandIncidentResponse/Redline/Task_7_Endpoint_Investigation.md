**Scenario:** A Senior Accountant, Charles, is complaining that he cannot access the spreadsheets and other files he has been working on. He also mentioned that his wallpaper got changed with the saying that his files got encrypted. This is not good news!

Are you ready to perform the memory analysis of the compromised host? You have all the data you need to do some investigation on the victim's machine. Let's go hunting!

Task:

1. Navigate to the folder on your desktop titled Endpoint Investigation.
2. Double-click on the AnalysisSession1.mans file. The data will be imported automatically into Redline.
3. Analyze the file to answer the questions below.


Question 1: 
Look in System Information and operating system information

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/f00ec1cc-5a27-416c-9bf9-8a3eea7afaf0)


Question 2: 
Look at File System and navigate to Charles Desktop; here, you will find several files. However, there is only one Txt file that will be the answer.

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/9e607e59-44d1-47c1-ae9f-1170d7248404)

Question 3: 
In the services tab, search for Windows Defender. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/c0ed5ceb-5da0-4297-8ddd-56ba750775ce)

Question 4: 
Go to the Downloads tab and search for Zip. 

Question 5: 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/0808611e-ace5-49e1-8aa0-dcef5d3bceec)

Questions 6: 
Go Back to the desktop and look for exe files

Question 7: 
Look at the exe details to obtain the hash

Question 8: 
Goto [VirusTotal](https://www.virustotal.com/gui/file/b3e1e9d97d74c416c2a30dd11858789af5554cf2de62f577c13944a19623777d/detection) and enter the M5 hash to obtain information about the executable. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/533769cb-83d4-4933-887f-bff7ff824b6c)



