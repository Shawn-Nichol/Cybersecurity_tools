Task 1-9 gives an overview of Volatility; no questions are asked during these tasks so that all relevant content will be stored in one repository. 

<h2>Connect to Volatility</h2>
Volatility is a free memory forensics tool developed and maintained by the Volatility Foundation, commonly used by malware and SOC analysts.

Connect to Volatility machine via SSH 
Navigate to the Opt Directory\Volaility3

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/0a114651-6b96-4c27-bbcd-d439de699553)


<h2>Plugins</h2>
Windows.info
- Provides system info
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/d4bb8cba-1848-4ace-aa45-0c2096dbbf92)

<h3>PListing Processes and Connections</h3>

**windows.pslist**
- gets the list of processes from the doubly-linked list that keeps track of processes in memory. 
- The output will include all current and terminated processes with thier exit times. 

**windows.psscan**
- This technique of listing will locate processes by finding data structures that match _eprocess.
- This technique can help with evasion countermeasures.

**windows.pstree**
- List all processes based on their parent process ID

**Windows.netstat**
- Identify the Network connections present at the time of extraction on the host machine.

**Windows.dlllist**
- List all DLL associated with processes at the time of extraction.

<h3>Volatility Hunting and Detection Capabilities</h3>

**windows.malfind**
- Identify injected processes and their PIDs along with the offset address, Hex, Ascii, and disassembly view of the infected area.
- The plugin scans the heap and identifies processes with the executable bit set RWE or RX.

**windows.yarascan**
- Compare memory file against Yara rules.

<h3>Advanced Memory Forensics</h3>

**windows.ssdt**
- search for hooking and output its results. 

**windows.modules**
- Will dump a list of loaded kernel modules
- This can be useful  in identifying active malware. However, if a malicious file is idly waiting or hidden, this plugin may miss it.

**windows.driverscan**
- scan for drivers present on the system at the time of extraction.
- This plugin can help to identify dirver files in the kernel that the modules plugin might have missed

**windows.modscan**
- plugin is used to scan the memory for loaded kernel modules or drivers.
- It helps in identifying loaded drivers and extracting information about them.

**windows.driverirp**
- plugin is used to display information about pending IRPs (Input/Output Request Packets) related to kernel drivers.
- This can be helpful for analyzing driver-level activity in the system.

**windows.callbacks**
- plugin is used to display registered callbacks in the Windows kernel.
- Callbacks are functions that are executed in response to specific events or conditions in the operating system.
- 
**windows.idt**
- plugin allows you to view and analyze the Interrupt Descriptor Table (IDT) in memory.
- The IDT is a data structure used by the CPU to manage interrupts and exceptions.

**windows.apihooks**
- plugin helps in identifying and analyzing API hooks that may have been set up by malware or other malicious software. 
- It can provide insights into how malicious code interacts with the system.


**windows.moddump**
- plugin is used to dump the memory contents of a loaded kernel module or driver.
- This can be valuable for further analysis of specific modules or drivers.


**windows.handles**
- plugin helps in listing and analyzing open handles (file handles, registry keys, etc.) in memory.
- This can provide insights into the resources accessed by processes.
