## Task 1 - Introduction
OpenVas is an application used to scan endpoints and web applications to identify and detect vulnerabilities. Corporations commonly use it as a mitigation solution to quickly identify gaps in their production or even development servers or applications. This is not an end-all-be-all-be-all solution, but it can help to get rid of any common vulnerabilities that may have slipped through the cracks. 


![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/b2d9d23e-0bd8-40d7-89d4-bc4178d54a52)

## Task 2 GVM Framework Architecture
OpenVAS is built of the GreenBone Vulnerability Management solution and is the only one of the appliances that is released from GreenBone. 

OpenVAS is a service within a larger framework of services known as Greenbone Vulnerability Managment (GVM). </br>
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/20d06819-220d-4e32-9d5f-cc704dbbcbcf)

Above is a brief visual breakdown of what the GVM framework looks like. Many components are a part of the architecture for the GVM framework, but we can break it down into three distinct sections Front-End, Back-End, and Vulnerability/Informatino feed. 

**Vulnerability/Information Feed (NVT,SCAP CERT, User Data, COmmunity Feed)**

This section will contain all information and vulnerability tests from the Greenbone community feed that will be the main baseline for testing against the system. This can also include User Data provided by the user in place of Greenbone NVTs and SCAP CERTs. 

**Back-End (OSP, OpenVAS, Targets)**
The back-end infrastructure is what will be actually conducting all of the vulnerability scanning and processing data and NVTS through oOpenVAS and GVM.

**Front-End (GSA, Web  Interfaces)**
This is what you ineract with when you navigate to OpenVAS in your browser. The web interfvaces are built off of the Greenbone Security Assistant and make life easier for an analyst or operator when working with OpenVAS or other forms of scanners through the GVM

https://forum.greenbone.net/t/about-gvm-10-architecture/1231


## Task 3 Installing OpenVAS

https://websiteforstudents.com/how-to-install-and-configure-openvas-on-ubuntu-18-04-16-04/

https://www.agix.com.au/installing-openvas-on-kali-in-2020/

## Task 4 Initial Configuration
Navigate to scans > Tasks and click on the purple magic wand icon to begin the basic configuration wizard. 

## Task 5 Scanning Infrastruture
sNow that we  know that
