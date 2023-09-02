Task 1
Redline is a tool developed by FireEye that will analyze a potentially compromised endpoint through the memory dump, including various file structures with a GUI. 

Redline can find the following
- Collect registry data (Windows only)
- Collect running processes
- Collect memory images (before win10)
- Collect Browser History
- Look for suspicious strings
- And more.

![image](https://github.com/Shawn-Nichol/Cybersecurity_tools/assets/30714313/5eb3e5b1-6540-440b-a232-8866311cee5b)


Task 2
  Collect Data options
  1. Create a Standard Collector: Configure the script to gather a minimum amount of data for analysis. 
  2. Create a Comprehensive Collector: Configure the script to gather the most data from your script. 
  3. Create an IOC Search Collector (Windows Only): This method collects data that matches the IOCs you create with the IOC Editor's help.
 

Standard instructions
"Create a standard Collector"
- Select OS platform

  
![image](https://github.com/Shawn-Nichol/Cybersecurity_tools/assets/30714313/d7af9769-3341-4f43-b5a3-71a0e2a08838)


- Edit script
There will be five tabs: Memory, Disk, System, Network, Other

![image](https://github.com/Shawn-Nichol/Cybersecurity_tools/assets/30714313/87c3e988-274c-432f-a588-173194d742b1)

Memory:
You can configure the script to collect memory data such as process listings, driver enumeration, and hook detection. 

![image](https://github.com/Shawn-Nichol/Cybersecurity_tools/assets/30714313/041e626b-7675-401d-9e9b-ff68dbac6e4e)

Disk:
This is where you can collect the data on Disk partitions and Volumes along with File Enumeration.

![image](https://github.com/Shawn-Nichol/Cybersecurity_tools/assets/30714313/0892140d-9139-49b2-93c6-e5df7f503e46)

System: 
The system will provide you with machine information.
- OS info
- Analyze system restore points
- Enumerate the registry hives (Windows version before 10 only)
- Obtain user accounts (Windows only)
- Obtain groups (OS X only)
- Obtain the prefetch cache (Windows Only)
  
![image](https://github.com/Shawn-Nichol/Cybersecurity_tools/assets/30714313/7871947e-26b7-49d6-bc30-0b3a3b632b29)


Network: 
Network options support Windows OS X and Linux platforms. You can configure the  script to collect network information and browser history, which is essential when investigating browser activities, including malicious file downloads and inbound/outbound connections. 

![image](https://github.com/Shawn-Nichol/Cybersecurity_tools/assets/30714313/94798460-aa44-4a06-9fa4-00da72f17e52)


Other: 
Collect the data on different services and tasks running on the system, including the hashes. 

![image](https://github.com/Shawn-Nichol/Cybersecurity_tools/assets/30714313/2d26cfc8-544b-4b11-a093-24d440098a75)


After configuration, select browser location (must be an empty file) and hit ok.

Review Results
Select "RunRedLineAudit.bat" as an administrator; this will open a cmd window that indicates that the script is running successfully and close when the data collection is done. This process can take 15 to 20 minutes. 

After the script is completed, open the newly generated session folder and select "AnalysisSession1".

![image](https://github.com/Shawn-Nichol/Cybersecurity_tools/assets/30714313/ef417318-009e-4089-9547-afdfc7ed1de2)

Task 3
Open Anasis file

![image](https://github.com/Shawn-Nichol/Cybersecurity_tools/assets/30714313/840c3bbb-8381-48f0-bcae-3dd251ec00d4)

Left panel 
- System information: information about the machine, BIOS (Windows only), OS, and user information
- Processes: Processes will contain attributes such as Process Name, PID, Path, Arguments, Parent process, username, etc.

A handle is a connection from a process to an object or resource in a Windows OS. OS use handles for referencing internal objects like files, registry keys, resources.

Memory solutions will let you investigate unsinged memory sections used by some processes. Many processes usually use legitimate DLLs, which will be signed. If you see an unsigned DLL, take a look. 

Strings show information on captured strings.

Ports This is where you review suspicious inbound and outbound connections. Threat actors like to avoid detection by hiding under system processes. For example, explorer.exe or notepad.exe shouldn't be on the processes with outbound connections list. 

Additional important sections
- File System
- Registry
- Windows Services
- Tasks
- Event logs
- ARP and Route Entries
- Browser URL history
- File Download history

![image](https://github.com/Shawn-Nichol/Cybersecurity_tools/assets/30714313/2e1025dc-903c-4d60-a2b8-47395d9f1e57)

Task 4
Navigate through the RedLine GUI to fine all the answers. 

![image](https://github.com/Shawn-Nichol/Cybersecurity_tools/assets/30714313/4704be3e-4df1-4bb1-aa75-1d958f94600d)

