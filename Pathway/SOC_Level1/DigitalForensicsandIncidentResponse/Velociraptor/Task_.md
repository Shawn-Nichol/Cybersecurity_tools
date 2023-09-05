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

Question 1: Which accessor can access hidden NTFS files and Alternate Data Streams? 
Look at the documentation for [Velociraptor VFS](https://docs.velociraptor.app/docs/gui/vfs/)

Answer: NTFS accessor

Question 2: Which accessor provides file-like access to the registry?
Look at the documentation for [Velociraptor VFS](https://docs.velociraptor.app/docs/gui/vfs/)

Answer: registry accessor

Question 3: What is the name of the file in $Recycle.Bin?

Navigate to the recycle.bin in VFS, be sure to refresh each directory as you go. 
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/0dbcb2fe-631d-458c-abcb-28030e5e0872)

Answer: Desktop.ini
Question 4: There is hidden text in a file located in the Admin's Documents folder. What is the flag?

Navigate to the administrator's document folder and look for a flag txt file. 
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/b6ad0d4b-9580-46e9-9a80-52d5e0e67226)

Answer: THM{VkVMT0NJUkFQVE9S}


Task 6

Question 1: What is followed after the SELECT keyword in a standard VQL query?

This information can be found in the documentation under [VQL Fundamentals](https://docs.velociraptor.app/docs/vql/)
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/a9e89317-ab00-44bc-b4a3-75e5801f8f52)

Answer: Column Selectors

Question 2: What goes after the FROM  keyword?

This information can be found in the documentation under [VQL Fundamentals](https://docs.velociraptor.app/docs/vql/)
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/745dca89-c433-4e1c-8b70-a4b9ccc64aba)

Answer: VQL Plugin

Question 3: What is followed by the WHERE keyword?

This information can be found in the documentation under [VQL Fundamentals](https://docs.velociraptor.app/docs/vql/)
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/d61f290d-e23a-47af-8ad8-58adc1ec6399)

Answer: Filter Expression

Question 4: What can you type in the Notepad interface to view a list of possible completions for a keyword?

This information can be found in the documentation under [VQL Fundamentals](https://docs.velociraptor.app/docs/vql/)
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/0b25759e-c817-489e-b508-0fc8df6e1892)

Answer:?

Question 5: What plugin would you use to run PowerShell code from Velociraptor?

This information can be found in the documentation under [Extending VQL](https://docs.velociraptor.app/docs/extending_vql/)
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/93da8531-01dd-45a1-882a-fbc2f9aa945b)

Answer: execve()


Task 7

Question 1: What are the arguments for parse_mft()?
This information can be found in the documentation under [NTFS Analysis](https://docs.velociraptor.app/docs/forensic/ntfs/)
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/066f2168-291e-4711-b068-9305e8ff3638)


Answer: parse_mft(filename="C:/$MFT", accessor="ntfs")

Question 2: What filter expression will ensure that no directories are returned in the results?
This information can be found in the documentation under [Searching Filenames](https://docs.velociraptor.app/docs/forensic/filesystem/)
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/95a137e8-feee-4f37-9249-3a9eb8d9ebcc)

Answer:IsDir

Task 8

Question 1: What is the name in the Artifact Exchange to detect Printnightmare?

You can search for vulnerabilities in the [Artifact Exchange](https://docs.velociraptor.app/exchange/) section of the documentation
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/7563f109-247f-4477-81fe-09b8f682c540)
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/48e20314-5cfa-428a-a79b-03987e7c2d2c)

Answer: Windows.Detection.PrintNightmare

Question 2: Per the above instructions, what is your Select clause? (no spaces after commas)
Use the Skelton query provided in the task and fill it out based on the instructions provided in the task. 

Answer: SELECT "C:/" + FullPath AS Full_Path,FileName AS File_Name,parse_pe(file="C:/" + FullPath) AS PE

Question 3: What is the name of the DLL that was  placed by the attacker?

Open velociraptor GUI
- CMD, navigate to the desktop dir
- run velociraptor.exe gui
- Accept risk

Create a new notebook and following vql query

SELECT "C:/" + FullPath AS Full_Path,FileName AS File_Name,parse_pe(file="C:/" + FullPath) AS PE FROM parse_mft(filename="C:/$MFT", accessor="ntfs")
WHERE NOT IsDir 
    AND FullPath =~ "Windows/System32/spool/drivers" 
    AND PE

Next scroll through the result until you find a suspicious DLL

Answer: nightmare.dll

Question 4: What is the PDB entry?

PDB info can be found in the DLL entry from the previous question. 
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/cac46e34-5b6a-41cc-9132-a0f632acc070)

Answer: C:\Users\caleb\source\repos\nightmare\x64\Release\nightmare.pdb
