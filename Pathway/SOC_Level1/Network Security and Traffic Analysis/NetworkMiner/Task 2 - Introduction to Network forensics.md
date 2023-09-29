Network forensics is a specific subdomain of the forensics domain that focuses on network traffic investigation. Network Forensics discipline covers accessing information transmitted by listening and investigating live and record traffic, gathering evidence/artifacts, and understanding potential problems. 

Briefly, it is the action of recording packets of network traffic, creating investigatable sources, and establishing a root-cause analysis of an event. The ultimate goal is to provide sufficient information to detect malicious activities, security breaches, policy/regulation compliance, system health, and user behavior.

Investigation tries to answer the 5 w. 
- Who (source IP and port)
- What (data/payload)
- Where (Destination IP and Port)
- When (time and data)
- Why (How/What happened)

### Network Forensics Use Cases
**Network Discovery:** Discovering the network to overview connected devices, rogue hosts, and network load.

**Packets reassembling:** Reassembling the packets to investigate the traffic flow. This use case is helpful in unencrypted traffic flows.

**Data Leakage detection:** Reviewing packet transfer rates for each host and destination address helps detect possible data leakage.

**Anomaly and Malicious Activity detection:** Reviewing overall network load by focusing on used ports, source, and destination addresses, and data helps detect possible malicious activities along with vulnerabilities. This use case covers the correlation of indicators and hypotheses as well.

**Policy/Regulation compliance control:** Reviewing overall network behavior helps detect policy/regulation compliance.

### Challenges of Network Forensics.
**Deciding what to do**: One of the most difficult challenges of network forensics is Deciding what to do. There are several purposes for carving networks; SOC, IH?IR and Threat Hunding. Observing, trapping, catching, or stopping an anomalous activity is also possible. 

**Sufficient data/evidence collection on the network**: One of the advantages of network forensics is the Ease of collecting evidence. However, the breadth of this concept poses a challenge. There are multiple points to consider in data/evidence collection.

**Short data capture:** One of the challenges in data/evidence collection. Capturing all network activity is not applicable and operable. It's not always possible to have the data capture coverage during pre and post-event. 

**Unavailability of full-packet capture on suspicious events:** Continuously capturing, storing, and processing full-packets costs time and resources. The inability to have full-packet captures for a long time creates time gaps used instead of full-packet captures to reduce the weight of having full-packet captures and increase the capture time. 

**Encrypted traffic:** Discovering the contents of encrypted data is not possible. However, the encrypted data still can provide valuable information for the hypothesis, like source and destination address and used service. 

** GDPR and Privacy concerns in traffic recording:** Capturing the traffic is the same as "recording everything on the wire"; therefore, this act should comply with GDPR and Business-specific regulations

** Nonstandard port usage: Sometimes hackers use nonstandard ports and services to avoid detection and bypass security mechanisms. 

** Time zone issues:** Using a common time zone is important for big-scale event investigation. Especially when working with multiple resources over different time zones, usage of different time zones creates difficulties in event correlation

**Lack of Logs**: Network forensics is not limited to investigating the network traffic data. Network devices and event logs are crucial in event correlation and investigation hypotheses. 


## Sources of Network Forensics Evidence
- TAPS
- Inline Devices
- SPAN Ports
- Hubs
- Switches
- Routers
- DHCP Servers
- Name Servers
- Authentication servers
- Firewalls
- Web Proxies
- Central Log servers
- Logs IDS/IPS application OS devices


## Primary purposes of Network Forensics
**Security operations SOC**:  Daily Security monitoring activities on system performance and health, user behavior, and security issues. 

**Incident Handling/Response and Threat Hunting:** During/Post-incident investigation activities on  understanding the reason for the incident detecting malicious and suspicious activity, and investigating the dat flow content. 

There are three main data types investigated in Network Forensics
- Live Traffic
- Traffic captures (full packet captures and network flows)
- Log Files

