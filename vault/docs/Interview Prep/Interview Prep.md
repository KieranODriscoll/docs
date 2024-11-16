## Manager Prep

## Technical Interview

### Incident Response
- NIST SP800-61
	- Incident Response Lifecycle
	- Lifecycle:
		- Preparation
		- Detection and Analysis
		- Containment, Eradication, Recovery
		- Lessons Learned /; Post-Incident Activity
### Preparation
- Communication methods
	- Phone numbers, Emails
	- How to alert other team members
- Incident handling hardware / software
	- Laptops, removable media, forensics software
- Incident Analysis resources
	- Documentation, network diagrams, baselines, critical file hash values
- Incident mitigation software
	- Clean OS and application images
- Policies needed for incident handling
	- Outlines what everyone needs to know and what they need to do
- Do we have the resources and plans in place to deal with the incident
## Detection / Identification
- Challenging step
- A large volume of data to analyze to determine if an event is truly an incident or not
- Use of tools to help (SIEM, EDR, XDR)
- Different levels of detail, different levels of perception
- Detection is often done by an automated tool, so analysis is the important step for triage analysts
- Has the threat and the threat actor been correctly identified in order for us to respond
### Analysis / Identification
- Attack is underway, or exploit was successful
- Detection occurred, further investigation required
- Has the threat and the threat actor been correctly identified in order for us to respond
### Isolation and Containment
- Want to reduce the spread of an incident, disconnect infected systems from the network to contain the incident
- Use sandboxes to isolate malware to investigate the malware's actions (Can be tricky, malware can sometimes detect that a sandbox is present)
- Containing the incident allows time to analyze, correct and fix without chance for further spread.
- Can the threat/security incident be contained to prevent other systems or users from being impacted
### Eradication / Recovery
- Returning things back to normal
- Fix vulnerabilities, no point bring a system back online if it is still vulnerable
- Remove malware
- Disable breached user accounts
- Recover the system
	- Restore from backups
	- Rebuild from scratch
- Remove the active threat
- Perform a full review of the impacted systems to return to business as usual operations
### Lessons Learned
- After every incident, lessons learned should be conducted
- What happened, exactly?
- How did the incident plans work, what went well, what could be improved
- Is there an indicator that should be watched more closely
- Involves everyone affected by the incident

## From ChatGPT
### Steps to Triage an Incident:
- Identify and assess: Determine the nature of the alert, confirm if it is malicious or legitimate
- Gather evidence: Collect logs, run memory dumps, or use forensic tools like Volatility
- Contain: Suspected malware outbreak, disconnect affected system from the network while ensuring forensic data isn't lost
- Analyze: Use tools like YARA for IoC hunting or compare logs against known IoCs
### Containment, Eradication, Recovery:
- Containment example: Quarantine a compromised endpoint by blocking its IP on firewall
- Eradication example: Remove malware using endpoint detection and response tools, or manually
- Recovery example: Reimage systems and validate restoration using backups
### Prioritizing incidents:
- Consider business impact: Malware alert on CEOs laptop probably take precedence over a generic phishing attempt
- Leverage frameworks like CVSS to evaluate
## Networking
- TCP vs UDP
	- TCP ensures delivery through acknowledgements and retransmissions. Establishes a connection before transmitting data through a 3 way handshake (File transfers, web pages)
	- UDP prioritizes speed over reliability, it does not establish a connection and is just a best effort transmission protocol. Not suited for services that require 100% transmission. (DNS, Video conferencing)
- Common ports
	- 80, 443, 22 are all ports that are typically open to allow HTTP/HTTPs and SSH traffic in and out of a network. Especially 80, 443.
	- Attackers exploit open ports, these are commonly open ports
	- Other common ports are also important: 3389 (RDP), 53 (DNS), etc. Knowing ports aids detection
## Perimeter Security
### Securing the perimeter
- Deploy firewalls, IDS/IPS, anti-malware systems
	- Stateful - Tracks established sessions, maintains TCP handshake state
	- Stateless - Examines packets individually, look at source/destination IP/Port.
- Conduct regular vulnerability scans and apply patches. 
- Next-gen firewall (NGFWs) to inspect traffic at Layers 4-7. Application aware, content inspection through certificates, decrypting traffic
- Can include physical security as well
	- Access control for building through locks, badges, etc
	- Man traps, access control vestibules
	- Security cameras, motion detectors, Fences, security guards, etc
- Defense in depth, layered approach
- Zero Trust Architecture
- Managed Service Provider, Arctic Wolf Solutions, Crowdstrike, etc
- EDR/XDR on endpoints
## Authentication
- MFA
- SSO
## General Cybersecurity Principles
- CIA Triad
	- Confidentiality: Protect sensitive data (encryption)
	- Integrity: Ensure data accuracy (hashing)
	- Availability: Ensure uptime (backups, DDoS protection)
- Principle of Least Privilege
	- Grant minimum necessary permissions
	- Reduces risk of insider threats and later movement
- Vulnerability, Exploit, Threat
	- Vulnerability: weakness in a system
	- Exploit: Method to leverage a vulnerability
	- Threat: Actor or event that could cause harm
## Network Monitoring Tools
- Examples:
	- Wireshark, Zeek
- Help detect anomalies like unusual data sizes or frequencies
- Allows insight into the traffic moving across an interface
## Packet Sniffers
- Monitor network traffic
- Can be misused for eavesdropping
- Analyze packets, look for unexpected payloads or suspicious communication patterns
- Can observe HTTP traffic carrying credentials and implement fixes like TLS/SLL encryption
## Encryption tools
- Symmetric vs Asymmetric
- MitM Attack Prevention
	- Use SSL/TLS, certificate pinning, and secure key exchanges
- Decrypting traffic
	- SSL/TLS key or decrypt in controlled environments
## SIEM
- Key features
	- Centralized log collection, correlation, and alerting
	- Splunk, Elastic Stack, QRadar, Wazuh
- Monitoring Unauthorized Access
	- Set up rules to flag login attempts from unusual locations or times
- Analyzing logs
	- Example: Identified failed login attempts followed by a successful one from the same IP. Investigate and confirm brute force