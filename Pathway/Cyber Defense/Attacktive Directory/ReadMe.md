# Attacktive Directory

This guided walkthrough on enumerating data on an Active Directory (AD) server and obtaining the necessary information to elevate privileges within a domain. This exercise will equip you with essential skills in understanding the AD environment, identifying vulnerabilities, and elevating your privileges effectively.

##Tools Used and Instructions
### 1. Nmap Enumeration:
Tools: Nmap
Instructions: Use Nmap to scan the target system for open ports and running services. Identify potential entry points and services vulnerable to exploitation.

### 2. Enum4linux Exploration:
Tools: Enum4linux
Instructions: Employ Enum4linux to enumerate local hosts and gather detailed information about the AD domain. Identify domain users and groups, providing a foundation for further exploration.

### 3. Kerbrute User Enumeration:
Tools: Kerbrute
Instructions: Install Kerbrute and run it with a user list to identify user accounts on the AD. Enumerate users to identify potential targets for privilege escalation.

### 4. HashCat Hash Analysis:
Tools: HashCat
Instructions: Use HashCat to analyze identified hashes, aiming to crack and reveal password information. Decrypt the hashes, providing valuable credentials for accessing the system.

### 5. SMBclient Data Extraction:
Tools: SMBclient
Instructions: Utilize SMBclient to access server shares and extract critical information. Copy essential files and data back to the local attacking computer for analysis.

### 6. Base64 Decoding:
Tools: Base64 Decode
Instructions: Apply Base64 decoding to any encoded credentials or sensitive data found on the server. Decode backup credentials, providing access to hidden information.

### 7. Secretsdump Password Hash Extraction:
Tools: Secretsdump
Instructions: Use Secretsdump to obtain password hashes of confirmed user accounts. Analyze the extracted hashes for potential vulnerabilities and weaknesses.

### 8. Evil-WinRM Privilege Escalation:
Tools: Evil-WinRM
Instructions: Leverage Evil-WinRM for pass-the-hash attacks, gaining access to the system using identified password hashes. Escalate privileges within the domain, gaining control over the targeted environment.
