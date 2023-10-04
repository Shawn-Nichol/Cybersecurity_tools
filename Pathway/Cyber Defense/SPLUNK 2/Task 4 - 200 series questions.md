
## Question 1

What version of TOR Browser did Amber install to obfuscate her web browsing? Answer guidance: Numeric with one or more delimiters.
```
index="botsv2" amber tor install
|  sort _time
```
Answer: 7.0.4

## Question 2

What is the public IPv4 address of the server running www.brewertalk.com?
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/109168db-be6d-4acb-ac3f-fd84272f5af1)

Answer: 54.42.208.228

## Question 3
Provide the IP address of the system used to run a web vulnerability scan against www.brewertalk.com? 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/570104eb-16c6-414b-8bc4-e3da51f542e6)
Look for the IP that has sent the most traffic; this would indicate some scanning. 

Answer: 45.77.65.211

## Question 4

Provide the IP address of the system used to run a web vulnerability scan against www.brewertalk.com.
Look for the URI with the most traffic; this is mostly like the URI that is trying to be exploited. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/a92b87ad-493b-4ebb-98e3-60b44481a453)

Answer: /member.php

## Question 5
The IP address from Q#2 is also being used by a likely different piece of software to attack a URI path. What is the URI path? Answer guidance: Include the leading forward slash in your answer. Do not include the query string or other parts of the URI. Answer example: /phpinfo.php

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/787193ef-63b1-4a70-8ca8-a7f3b065ac9b)
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/6655f68a-f16d-4e44-9550-8c4e534997a1)

Answer: updatexml

## Question 6
What was the value of the cookie that Kevin's browser transmitted to the malicious URL as part of an XSS attack? Answer guidance: All digits. Not the cookie name or symbols like an equal sign.

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/4d07f9b0-6ff0-4b4e-bac4-e4f639b67ba0)

Answer: 1502408189

## Question 7
What brewertalk.com username was maliciously created by a spear phishing attack?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/ee2c2388-767a-401c-bbec-e7a705e11366)

Answer: kIagerfield
