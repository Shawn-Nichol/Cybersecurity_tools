## Task 1
It is a vulnerability scanner that uses techniques similar to Nmap to find and report vulnerabilities, which are  then presented in a GUI

## Task 2 Installation Linux
https://docs.tenable.com/nessus/Content/GettingStarted.htm

** Restster account **  https://www.tenable.com/products/nessus/nessus-essentials
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/635bea1b-ef32-431b-8365-f4065fb1091a)

** Download Nessus** Nessus-#.##.#-debain6amd6f.db

** Install**
In the terminal navigate to the download folder and run the following command. 
```
sudo dpkg -i package_file.deb
```

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/883c8f7d-4188-4fd4-a0b2-b92d480a8acc)

** Start Nessus**
```
sudo /bin/systemctl start nessusd.service
```

** open Fire fox** and goto https://localhost:8834


**Set up the scanner**
Select Nessus Essentials
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/6f434f44-f2ff-4174-90a8-968495ceba43)

**Register** install
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/6d13f9a3-af2b-4e49-a7cf-cd01320605cb)

**Fill out username and password**
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/cc2843ff-8d99-47f8-921a-b99602abba0b)


**Nessus will install plugins**
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/76576cb9-7f7e-4e72-960c-cfe3a69a064c)

**Login**
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/43a71643-d7a0-4a76-91bb-711ec0702707)

## Task 3 Navigating scans
Question: What is the name of the button which is used to launch a scan?
Answer: New Scan

Question: What side menu option allows us to create custom templates?
Answer: Policies

Question What menu allows us to change plugin properties, such as hiding them or changing their severity?
Answer: Plugin Ruels'

Question: In the Scan templates section, after clicking on 'New Scan', what scan allows us to see simply what hosts are alive?
Answer: Host Discovery

Question: One of the most useful scan types, which  is considered to be suitable for any host?
Answer: Basic Network Scan

Question: What scan allows you to authenticate to hosts and enumerate missing updates?
Answer: Credentialed Patch Audit

Question: what scan is specifically used for scanning Web Applications?
Answer: Web Application Tests


## Task 4 Scanning
Question: Create a new Basic network scan targeting the deployed VM. What option can we set under Basic to set a time for this scan to run? This can be very useful when network congestion is an issue.
Answer: Schedule

Question: Under Discovery, set the scan type to cover ports 1-65535. What is this type called?
Answer: Port scan (all ports)

Question: What scan type can we change to under advanced for lower bandwidth connections?
Answer: scan low-bandwidth links

Question: After the scan completes, which vulnerability in the Port scanners family can we view the details of to see the open ports on this host?
Answer: Nessus SYN scanner

Question: What Apache HTTP server version is reported by Nessus?
Answer: 2.4.99



## Task 5
Question: What is the plugin ID of the plugin that determines the HTTP server type and version?
Answer:10107

 Question: What authentication page is discovered by the scanner that transmits credentials in cleartext?
 Answer: login.php

Question: What is the file extension of the config backup?
Answer: .bak

Question: Which directory contains example documents? 
Answer: /external/phpids/0.6/docs/examples/

Question: What vulnerability is this application susceptible to that is associated with X-Frame-Options?
Answer: clickjacking

