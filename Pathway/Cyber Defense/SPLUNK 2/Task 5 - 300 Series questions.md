Question: 
Mallory's critical PowerPoint presentation on her MacBook gets encrypted by ransomware on August 18. What is the name of this file after it was encrypted?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/d5a80ce4-79a6-42ed-8a59-8621072e46fe)


Answer: Frothly_marketing_campaign_Q317.pptx.crypt_


Question: 
There is a Games of Thrones movie file that was encrypted as well. What season and episode is it?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/9fd4d107-df3e-42d9-90bb-05712dad377f)


![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/24f89d97-5683-42ad-a0e1-9800466dd7ae)

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/bf32fca7-8bf1-4cb0-916c-576f7fb7f39d)

Google the ID. 

Answer: Alcor Micro Corp.

Question: 
Kevin Lagerfield used a USB drive to move malware onto Kutekitten, Mallory's personal MacBook. She ran the malware, which obfuscates itself during execution. Provide the vendor name of the USB drive Kevin likely used. Answer Guidance: Use time correlation to identify the USB drive.

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/c5dc38d1-1f96-468d-b4be-f4ffdcbe1f34)

Then, google the ID to find the vendor. 

Answer: Alcor Micro Corp.

Question
What programming language is at least part of the malware from the question above written in?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/6e25a687-22bb-451a-b9d1-52504979bce7)

Use the Columns.sha256 or other interesting fields that contain hashes. 
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/b819bf63-20d2-4efa-9571-6243d553afd7)

Plug the hash into VirusTotal to get details on the hash. 
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/0c42dec4-cc92-433d-b462-91cb7f5dbf6d)

Answer: Peal


Question
When was this malware first seen in the wild?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/13e80ad5-c174-493d-915b-a5f86941611e)
Answer: 2017-01-17


Question:

The malware infecting kutekitten uses dynamic DNS destinations to communicate with two C&C servers shortly after installation. What is the fully-qualified domain name (FQDN) of the first (alphabetically) of these destinations?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/c33125e7-58a2-4488-bc3d-936d7a14e75f)


Answer: eidk.duckdns.org

Question:
From the question above, what is the fully-qualified domain name (FQDN) of the second (alphabetically) contacted C&C server?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/67256b81-e75c-4ad2-8906-f69d5983359d)


Answer: eidk.hopto.org
