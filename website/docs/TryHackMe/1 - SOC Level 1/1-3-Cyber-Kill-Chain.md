# 1.3 - Cyber Kill Chain
## Introduction
![Pasted_image_20241006141033](//assets/Pasted_image_20241006141033.webp)
- Kill chain is a military concept related to the structure of an attack
- Consists of target identification, decision and order to attack the target, finally the target destruction
- Cyber kill chain defines the steps used by adversaries or malicious actors in cyberspace
- To succeed, an adversary needs to go through all phases of the Kill Chain
- Knowing the attack phases helps you better understand adversaries and their techniques used in the attack to defend yourself
- The cyber kill chain will help you understand and protect against ransomware attacks, security breaches as well as Advanced Persistent Threats (APTs)
- Can use the cyber kill chain to assess your network and system security by identifying missing security controls and closing certain security gaps based on company's infrastructure
- Help you recognize the intrusion attempts and understand the intruder's goal and objectives
- Attack phases:
	- Reconnaissance
	- Weaponization
	- Delivery
	- Exploitation
	- Installation
	- Command & Control
	- Actions on Objectives (Exfiltration)
## Reconnaissance
- Discovering and collecting information on the system and victim
- Planning phase for adversaries
- **OSINT** (Open-Source Intelligence) also falls under reconnaissance
	- First step an attacker needs to complete to carry out further phases
	- Collect every available piece of information on company from publicly available resources
- Email harvesting
	- Process of obtaining email addresses from public, paid or free services.
	- Can use email address harvesting for a phishing attack
	- Examples
		- theHarvester
		- Hunter.io - email hunting tool to obtain contact info associated with the domain
		- OSINT framework - provides collection of OSINT tools
## Weaponization
- "weaponizer" combines malware and exploit into a deliverable payload
- Most attackers use automated tools to generate the malware or refer to the DarkWeb to purchase the malware
- Sophisticated actors and nation-sponsored APT would write their custom malware to make the malware sample unique and evade detection on the target
- Malware is a program or software that is designed to damage, disrupt or gain unauthorized access to a computer
- An exploit is a program or a code that takes advantage of the vulnerability or flaw in the application or system
- A payload is a malicious code that attacker runs on the system
- In the weaponization phase, the attacker would:
	- Create an infected Microsoft Office doc containing malicious macro
	- Can create a malicious payload or a very sophisticated worm, implant it on a USB drive and distribute them in public
	- Would choose C2 techniques for executing commands on victim machines or delivering more payloads
	- Would select a backdoor implant (gain access to system, including bypassing the security mechanisms)
## Delivery
- Choosing the method for transmitting the payload or malware
- Options to choose from:
	- Phishing email
		- Reconnaissance would determine the targets for the attack, either the whole company, some people or a specific person (spearphishing)
		- Email would contain a payload or malware
	- Distributing infected USB drives or in a company parking lot, etc
	- Watering hole attack
		- Targeted attack designed to aim at a specific group of people by compromising the website they usually visit. Redirect them to the malicious website of the attacker's choice
## Exploitation
- To gain access to a system, attacker needs to exploit the vulnerability
- Phishing emails where a victim falls for it, gaining access to system
- Once access is gained, attacker could exploit software, system, or sever-based vulnerabilities to escalate privileges or move laterally through the network
- Lateral movement - techniques that an attacker uses after gaining initial access to the victim's machine to move deeper into a network to obtain sensitive data
- OWASP Top 10 for server-based and web-based vulnerabilities
- Could also apply a Zero-day exploit at this stage
	- Unknown exploit, no opportunity for detection at the beginning
- Examples of how to carry out exploitation
	- Victim triggers the exploit by opening the email attachment, or clicking a link
	- Using a zero-day
	- Exploiting software, hardware, or human vulnerabilities
	- Attacker triggers the exploit for server-based vulnerabilities
## Installation
- Once getting access to a system, they would want to reaccess the system if connection is lost or if detected and initial access is removed, or even the original entry point is patched
- Installation of a persistent backdoor will let the attacker access the system compromised previously
- Can be achieved by:
	- Installing a web shell on the webserver. Used to maintain access to the compromised system. Web shell simplicity and file formatting  (.php, .asp, .aspx, .jsp, etc) can be difficult to detect and might be classified as benign
	- Installing a backdoor on the victim's machine. Could use Meterpreter to gain an interactive shell from which an attacker can interact with the victim's machine remotely
	- Creating or modifying windows services. Creates or modifies the Windows services to execute the malicious script or payloads regularly as part of the persistence.
		- Can use tools like sc.exe and Reg to modify service configurations
		- Can masquerade the payload by using a service name that is known to be related to the OS or legitimate software
	- Adding entry to the "run keys" for the malicious payload in the Registry or the Startup Folder. Executing it whenever the user logs into the computer.
		- A system wide startup folder and an individual user folder
- Can use Timestomping technique to avoid detected by the forensic investigator and make the malware appear as part of a legitimate program.
	- lets an attacker modify the file's timestamps, including modify, access, create and change times
## Command & Control
- Channel through malware to remotely control and manipulate the victom
- Term is known as C&C, C2 Beaconing as a type of malicious communication between a C&C server and malware on the infected host
- Infected host will consistently communicate with the C2 server
- Compromised endpoint would communicate with external server setup byattacker
- Common C2 Channels:
	- HTTP on port 80 or HTTPS on port 443 - blends malicious traffic with legitimate traffic. Can help evade firewalls
	- DNS - Infected machine makes constant DNS requests to the DNS server that belongs to an attacker, this type of C2 communication is also known as DNS Tunneling
## Actions on Objectives (Exfiltration)
- Collect credentials from users
- Perform privilege escalation
- Internal reconnaissance
- Lateral movement through the company's environment
- Collect and exfiltrate sensitive data
- Deleting the backups and shadow copies. Shadow Copy is a Microsoft technology that can create backup copies, snapshots of computer files, or volumes
- Overwrite or corrupt data
## Practical Analysis
![Pasted_image_20241006151002](//assets/Pasted_image_20241006151002.webp)
