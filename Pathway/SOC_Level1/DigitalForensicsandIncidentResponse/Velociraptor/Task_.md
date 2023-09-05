Open source endpoint monitoring, digital forensics, and cyber response platform. 


Task 2 Question 1: How would you launch an instant Velociraptor on Windows using the documentation?
[Velociraptor Documentation](https://docs.velociraptor.app/docs/deployment/#instant-velociraptor)

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/9be8f854-cdfb-4638-a690-185c980a9886)

Task 3
Question 1: What is the hostname for the client? 

From the client overview, select the desired host, and computer info will be displayed. 
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/ad0f152d-5736-47c2-8c28-6b13229bd9c2)

Answer: thm-velociraptor.eu-west-1.compute.internal

Question 2: What is listed as the agent version? 

The same screen will display the answer.
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/fef10fb3-0e56-4468-b610-597feaf3c7df)

Answer: 2021-04-11T22:11:10Z

Question 3: In the collected tab, what was the VQL command to query the client user accounts? 

Navigate to the Collected tab and select the first entry.
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/9428f3bc-e087-4c6d-93fa-ad89d4741b54)

Select the request tab to view VQL commands
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/c71be83f-a9f6-4311-bcf7-10fbd0d67c74)

Answer: LET Generic_Client_Info_Users_0_0=SELECT Name, Description, Mtime AS LastLogin FROM Artifact.Windows.Sys.Users()

Question 4: In the Collected tab, check the results for the PowerShell whoami command you executed previously. What is the column header that shows the output of the command?

Navigate to the collected tab, and select windows powershell entry. 
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/8bfa49d9-b733-4657-979c-e1974e6414b1)

Select the Notebook tab; this is going to be the column. 
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/152c7151-a3db-42e5-be4a-f47367538fe7)

Answer: stdout

Task 4

Question 1: Earlier you created a new artifact collection for Windows.KapeFiles.Targets. You configured the parameters to include Ubuntu artifacts. Review the parameter description for this setting. What is this parameter specifically looking for?

Use the description from the Ubuntu resource that was selected. 
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/0378c33a-0bdd-4529-b259-c16c230896d3)

Answer: Ubuntu on Windows Subsystem for linux

Question 2: Review the output. How many files were uploaded?

Scroll to the bottom of the uploaded files tab to see the amount of files uploaded. 
Answer: 20

Task 5
