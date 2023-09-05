Prep work for case one. 

First, establish an SSH session with the Volatility computer. 
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/d199083d-3eb8-40e0-a56e-e54c8f378187)

Navigate to the Voaltility3 folder
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/3b0f9b6b-d36a-49b1-b8f2-7dfabcc0a89b)

Question 1: What is the build version of the host Machine in Case 001?

Use the info plugin to provide system info. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/cbc6882b-05a5-421a-b95f-393373b4666d)

Question 2: At what time was the memory file acquired in Case 001?

Use the info plugin to provide system info. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/b8ad7d23-a315-44d0-b5a4-0a11abb192f1)

Question 3: What process can be considered suspicious in Case001?
The scenario notes that we are looking for a process masquerading as an Adobe document. 

Use the psscan plugin to provide a list of processes. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/a02090ad-6bee-4c5a-9cf9-b9c8d7f0b192)

Question 4: What is the parent process of the suspicious process in Case 001?


Use the pstree plugin to list all process based on the parent process.

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/01d33b25-6167-4467-bc87-858ab71468fb)

Question 5: what is the PID of the suspicious process in Case 001? 

The PID can be found in the results from the last query. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/c0adeacd-b665-45dd-89b0-df901efc35f2)

Question 6: What is the parent process PID in Case 001?

The PPID can be found in the results from the last query. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/7377c726-6cc7-460e-a2a1-c820f248c0f0)

What user-agent was employed by the adversary in Case 001? 

Step one, dump the memmap into a directory. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/c25cb78c-a3ff-4467-a937-c9647a57dcbb)

Step two is to filter through the recently dumped data into the tmp directory. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/c0d5f7d9-964f-4fac-956e-c648637fb64f)


Question 7: Was Chase Bank one of the suspicious bank domains found in Case 001?

Filter through the data looking for Chase. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/d9bcbc0e-e482-4940-bc3b-6ae0701e1a57)


Question 8: What suspicious process is running at PID 740 in Case 002?

Use the psscan plugin to list processes and match the process to PID 740.

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/85a5d158-3e41-418d-bbd3-2ce681112713)

Question 9: What is the full path of the suspicious binary in PID 740 in Case 002?

Use the dlllist plugin and filter for PID 740. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/824b4cdd-69b6-426a-b077-dd7918128ece)


Question 10: What is the parent process of PID 740 in Case 002?

Use the pstree plugin to identify the parent process. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/83ce8d53-e168-4c8e-b79d-34920016e9d7)


Question 11: From our current information, what malware is present on the system in Case 002? 

Google the @WanaDecryptor@. There will be a tone of information on it. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/ab127cd7-b976-40f5-a674-da454bda38d0)

[This link to bleeping computers provides a great deal of info.](https://www.bleepingcomputer.com/news/security/wannacry-wana-decryptor-wanacrypt0r-info-and-technical-nose-dive/)

Question 12: What is loaded by the decryptor used for socket creation in case? 

[Google Wannacry DLLs.](https://www.researchgate.net/figure/Dynamic-Link-Libraries-DLLs-invoked-by-WannaCrys-worm-component_tbl2_332028948)

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/beb7dd58-2451-4fc0-a861-cedf51d1001f)

Question 12: What mutex can be found that is a known indicator of the malware in Case 002?

Use the handles plugin and filter the data with the PID 1940. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/1c498072-3357-4903-b5a0-062676459752)

Scroll down till you find a mutant
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/7233ce03-4089-4564-8904-e075336f8381)

Question 13: What plugin could be used to identify all files loaded from the malware working directory in Case 002? 

windows.filescan






