# 1.2 - Pyramid of Pain
## Introduction
- Pyramid of Pain is being applied to cybersecurity solutions to improve the effectiveness of CTI (Cyber Threat Intelligence), threat hunting, and incident response exercises
## Hash Values (Trivial)
- a numerical value of fixed length that uniquely identifies data
- Algorithms
	- MD5
		- Not cryptographically secure
		- Has collision
	- SHA-1
		- Deprecated
		- Susceptible to brute force attacks
	- SHA-2
		- Has many variants
		- SHA-256 is most common
	- SHA-3
- A hash is not considered cryptographically secure if two files have the same hash value or digest
- Hashes are used to gain insight into a specific malware sample, a malicious or suspicious file and as a way to uniquely identify and reference malicious artifacts
- However, an attacker can modify a file by even a single bit which is trivial and this would result in a different hash value
- Threat hunting using file hashes as the IOC (Indicators of compromise) can become difficult
## IP Addresses (Easy)
- In the Pyramid of Pain, IP addresses are indicated with the color green
- Knowledge of the IP addresses an adversary uses can be valuable
- Common defense tactic is to block, drop or deny inbound requests from the IP addresses on your parameter or external firewall
- Not bulletproof, trivial for an adversary to recover simply by using a new public IP address
- Fast Flux
	- a DNS technique used by botnets to hide phishing, web proxying, malware delivery, and malware communication activities behind compromised hosts acting as proxies
	- Purpose of the Fast Flux network is to make the communication between malware and its C2 challenging to be discovered by security professionals
	- Primary concept is having multiple IP addresses associated with a domain name, which is constantly changing
## Domain Names (Simple)
- Transition of colors - green to teal
- Simply a mapping of an IP address to a string of text
- More of a pain for the attacker to change, as they would need to purchase a domain, register it, modify DNS records
- Unfortunately for defenders, many DNS providers have loose standards and provide APIs to make it easier for the attacker to change the domain
- Punycode is a way of converting words that cannot be written in ASCII, into a Unicode ASCII encoding, allowing attackers to make a domain name look very similar to the real thing
![](assets/Pasted%20image%2020241006112558.png)
![](assets/Pasted%20image%2020241006112608.png)
- Modern web browser are pretty good at converting the obfuscated punycode to its full domain name
- To detect malicious domains, proxy logs or web server logs acn be used
- URL Shorteners are another way to hide malicious domain names
	- Can see the actual website the shortened link is redirecting to by appending a "+" at the end of the URL
- Any.run is a sandboxing tool that can execute samples
	- Can review any connections such as HTTP requests, DNS request or processes communicating with an IP address
	- HTTP requests
		- Useful to see what resources are being retrieved from a webserver, such as a dropper or a callback
	-  Connections
		- shows any communications made since the detonation of the sample
		- Useful to see if a process communicates with another host
	- DNS Requets
		- Malware often makes DNS requests to check for internet connectivity
## Host Artifacts (Annoying) 
- Yellow Zone
- Attackers will feel a little more annoyed and frustrated if you can detect the attack
- They will need to circle back and change the attack tool and methodologies which is time-consuming
- Host artifacts are the traces or observables that attackers leave on the system
	- Registry values
	- Suspicious process executon
	- Attack patterns
	- IOCs
	- Files dropped by malicious applications
	- Anything exclusive to the current threat
## Network Artifacts (Annoying)
- Yellow zone in the pyramid of pain
- If you can detect and respond to the threat, the attacker would need more time to go back and change his tactics or modify is tools
- This gives more time to respond and detect upcoming threats or remediate the existing ones
- A network artifacts can be:
	- User-agent string
		- A User-Agent string that hasn't been observed in your environment before or seems out of the ordinary
	- C2 information
	- URI patterns followed by HTTP post requests
- Can be detected in Wireshark PCAPs by using a network protocol analyzer such as TShark or exploring IDS logging from a source such as Snort
- HTTP POST containing suspicious strings
	- ![](assets/Pasted%20image%2020241006115948.png)
- Common User-Agents strings found for the Emotet Downloader Trojan
	- ![](assets/Pasted%20image%2020241006131815.png)
## Tools (Challenging)
- At this stage, we have levelled up our detection capabilities against the artifacts
- Would most likely give up trying to break into your network or go back and try to create a new tool that serves the same purpose
- Attackers would need to invest some money into building a new tool, finding a tool that has the same potential, or learn how to be proficient in a certain tool
- Attackers use utilities to create malicious macro documents for spearphishing, a backdoor that can establish a C2, custom .EXE and .DLL files, payload, password crackers
- Antivirus signatures, detection rules and YARA rules can be great weapons against attackers at this stage
- MalwareBazaar and Malshare are good resources to provide samples, malicious feeds and YARA results
- Detection rules can be found at SOC Prime Threat Detection Marketplace, shared detection rules for different threats
- Fuzzy hashing helps perform similarity analysis, match two files with minor differences based on the fuzzy hash values
	- SSDEEP is an example of fuzzy hashing
## TTPs (Tough)
- Final stage of Pyramid of Pain
- TTPs stands for Tactics, Techniques and Procedures
- Includes the whole MITRE ATT&CK Matrix
	- all steps taken by an adversary to achieve goal, starting from phishing attempts to persistence and data exfiltration
- If you can detect and respond to TTPs quickly, can leave adversaries almost no chance to fight back
- Two options for attackers if detected:
	- Go back, do more research and training, reconfigure their custom tools
	- Give up and find another target
## Practical: The Pyramid of Pain
- ![](assets/Pasted%20image%2020241006133453.png)