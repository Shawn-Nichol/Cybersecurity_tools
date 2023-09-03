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
