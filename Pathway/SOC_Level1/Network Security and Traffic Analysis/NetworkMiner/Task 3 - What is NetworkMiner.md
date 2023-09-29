Traffic sniffing: It can intercept the traffic, sniff it, and collect and log packets that pass through the network.
Parsing PCAP files: It can parse pcap files and show the content of the packets in detail.
Protocol analysis: It can identify the used protocols from the parsed pcap file.
OS fingerprinting: It can identify the used OS by reading the pcap file. This feature strongly relies on satori and p0f
File Extraction: It can extract images, HTML files and emails from the parsed pcap file
Credential grabbing: It can extract credentials form the parsed pcapap file
Clear text keyword parsing: It can extract cleartext keywords and strings from the parsed pcap file. 


Pros
- OS fingerprinting
- Easy file extraction
- Credential grabbing
- Clear Text keyword parsing
- Overall overview

Cons
Not useful in active sniffing
Not useful for large pcap investigation
limited filtering
Not built for manual traffic investigation.



| Feature                      | NetworkMiner               | Wireshark              |
|------------------------------|----------------------------|------------------------|
| **Purpose**                  | Quick overview, traffic mapping, and data extraction | In-Depth analysis      |
| **GUI**                      | ✅                         | ✅                     |
| **Sniffing**                 | ✅                         | ✅                     |
| **Handling PCAPS**           | ✅                         | ✅                     |
| **OS Fingerprinting**        | ✅                         | ❌                     |
| **Parameter/Keyword Discovery** | ✅                       | Manual                |
| **Credential Discovery**     | ✅                         | ✅                     |
| **File Extraction**          | ✅                         | ✅                     |
| **Filtering Options**        | Limited                    | ✅                     |
| **Packet Decoding**          | Limited                    | ✅                     |
| **Protocol Analysis**        | ❌                         | ✅                     |
| **Payload Analysis**         | ❌                         | ✅                     |
| **Statistical Analysis**     | ❌                         | ✅                     |
| **Cross-Platform Support**   | ✅                         | ✅                     |
| **Host Categorisation**      | ✅                         | ❌                     |
| **Ease of Management**       | ✅                         | ✅                     |
