# 1.4 - Unified Kill Chain
## Introduction
![](assets/Pasted%20image%2020241006192819.png)
- Understanding the behaviors, objectives, and methodologies of a cyber threat is a vital step to establishing a strong cybersecurity defense (known as a cybersecurity posture)
### Learning Objectives
- Understanding why frameworks such as the UKC are important and helpful in establishing a good cybersecurity posture
- Using the UKC to understand an attacker's, motivation, methodologies and tactics
- Understanding the various phases of the UKC
- Discover that the UKC is a framework that is used to complement other frameworks such as MITRE
## What is a "Kill Chain"
- Term used to explain the various stages of an attack.
- Used to describe the methodology/path attackers such as hackers or APTs used to approach and intrude a target
- Objective is to understand an attacker's "Kill Chain" so that defense measures can be put in place to either pre-emptively protect a system or disrupt an attacker's attempt
## What is "Threat modelling"
- A series of steps to ultimately improve the security of a system
- About identifying risk and essentially boils down to:
	- Identifying what system and applications need to be secured and what function they serve in the environment.
		- Is the system critical to normal operations, and is a system holding sensitive information like payment info or addresses
	- Assessing what vulnerabilities and weaknesses these systems and applications may have and how they could be potentially exploited
	- Creating a plan of action to secure these systems and applications may have and how they could be potentially exploited
	- Putting in policies to prevent these vulnerabilities from occurring again where possible
- Important procedure in reducing risk within a system or application
- High level-overview of an organization's IT assets and the procedures to resolve vulnerabilities
- UKC can encourage threat modelling, as it helps identify potential attack surfaces and how these systems may be exploited
- STRIDE, DREAD, CVSS are a few frameworks that are used in threat modelling
## Introducing the Unified Kill Chain
- Aims to complement other cybersecurity kill chin frameworks
- UKC as 18 phases to an attack: Reconnaissance to data exfiltration and understanding an attacker's motive
- Phases are grouped together in this room into a few areas of focus for brevity
- Modern and extremely detailed
- ![](assets/Pasted%20image%2020241006195817.png)
### Benefits of UKC
- Modern
- Extremely detailed
- Covers an entire attack - Reconnaissance -> Exploitation -> Post-exploitation and includes identifying an attacker's motivation
- Highlights a much more realistic attack scenario
	- Various stages will often re-occur
## Phase: In (Initial Foothold)
- Focuses on the phases for an attacker to gain access to system or network
- Attackers employ numerous tactics to investigate systems for potential vulnerabilities that can be exploited to gain a foothold
- ![](assets/Pasted%20image%2020241006200523.png)
- This series of phases also accommodates for an attacker creating a form of persistence
### Reconnaissance ([MITRE Tactic TA0043](https://attack.mitre.org/tactics/TA0043/))
- Describes the techniques that an adversary employs to gather information relating to their target
- Can be achieved through passive and active means
- Info obtained is used all throughout the later stages
- Information gathered can include:
	- What systems and services are running, beneficial in weaponization and exploitation
	- Contact lists or lists of employees, either for impersonation or phishing attacks
	- Potential credentials to use later, pivoting or initial access
	- Understand network topology that can be pivoted too
### Weaponization ([MITRE Tactic TA0001](https://attack.mitre.org/tactics/TA0001/))
- Phase describes the adversary setting up necessary infrastructure to perform an attack
- Setting up a C2, or system capable of catching reverse shells, delivering payloads
### Social Engineering ([MITRE Tactic TA0001](https://attack.mitre.org/tactics/TA0001/))
- Techniques used to manipulate employees to perform actions that will aid in the adversaries attack
- Social engineering attack:
	- Getting a user to open a malicious attachment
	- Impersonating a web page and having the user enter their credentials
	- Calling or visiting the target and impersonating a user, or being able to gain access to areas of a site that the attacker would not previously be capable of
### Exploitation ([MITRE Tactic TA0002](https://attack.mitre.org/tactics/TA0002/))
- Describes how an attacker takes advantage of weaknesses or vulnerabilities present
- Defines "exploitation" as abuse of vulnerabilities to perform code execution
- Uploading and executing a reverse shell to a web application
- Interfering with an automated script on the system to execute code
- Abusing a web app vulnerability to execute code on the system it is running on
### Persistence ([MITRE Tactic TA0003](https://attack.mitre.org/tactics/TA0003/))
- Describes techniques an adversary uses to maintain access to a system they have gained an initial foothold on
- Creating a service on the target to allow attacker to regain access
- Adding the target system to a C2 server where commands can be executed remotely
- Leaving other forms of backdoors that execute when a certain access occurs (ie. logging in)
### Defense Evasion ([MITRE Tactic TA0005](https://attack.mitre.org/tactics/TA0005/))
- One of the more valuable phases of the UKC
- Used to understand the techniques an adversary uses to evade defensive measures put in place in the system/network
	- Web application firewalls
	- Network firewalls
	- Anti-virus
	- Intrusion detection or prevention systems
- Valuable when analyzing an attack as it helps form a response and improvement to defense systems can be learned
### Command & Control ([MITRE Tactic TA0011](https://attack.mitre.org/tactics/TA0011/))
- Combines the efforts an adversary made during "Weaponization" stage to establish communications between target system and adversary
- Can establish C2 of a target system to achieve its action on objectives
	- Execute commands
	- Steal data, credentials or other information
	- Use the controlled server to pivot to other systems on the network
### Pivoting ([MITRE Tactic TA0008](https://attack.mitre.org/tactics/TA0008/))
- Technique an adversary uses to reach other systems within a network, that are not otherwise acceptable (ie. exposed to internet)
- Often many systems that are not exposed to the internet that contain valuable data and often have weaker security
- Example: gain access to a publicly accessible web server and then attack other systems within its network
## Phase: Through (Network Propagation)
- Follows a successful foothold being established on the target network0
- Would seek to gain additional access and privileges to systems and data
- Attacker would set up a base on one system to act as their pivot point and gain info about internal network
- ![](assets/Pasted%20image%2020241010105130.png)
### Pivoting ([MITRE Tactic TA0008](https://attack.mitre.org/tactics/TA0008/))
- Once access has been achieved
- Use system as a staging site and tunnel between their C2 and the victim's network
- Used as the distribution point for malware and backdoors for later stages
### Discovery ([MITRE Tactic TA0007](https://attack.mitre.org/tactics/TA0007/))
- Uncover information about the system and the network it is connected to
- Knowledge base would be built from the active users, permissions granted, applications in use, web browser activity, files, directories, network shares and system configurations
### Privilege Escalation ([MITRE Tactic TA0004](https://attack.mitre.org/tactics/TA0004/))
- Attempt to gain more prominent permissions within the pivot system
- Leverage information on the accounts present with vulnerabilities and misconfigurations found to elevate access to superior levels:
	- SYSTEM / Root
	- Local Administrator
	- User account with admin-like access
	- User account with specific access or functions
### Execution ([MITRE Tactic TA0002](https://attack.mitre.org/tactics/TA0002/))
- Stage where they deploy their malicious code using the pivot system as their host
- Remote trojan, C2 scripts, malicious links and scheduled tasks are deployed and created to facilitate a recurring presence on the system
### Credential Access ([MITRE Tactic TA0006](https://attack.mitre.org/tactics/TA0006/))
- Working hand in hand with the Privilege Escalation stage
- Attempts to steal account names and passwords. Keylogging and credential dumping
- Makes it harder to detect during their attack as it would come from legitimate credentials

### **Lateral Movement** ([MITRE Tactic TA0008](https://attack.mitre.org/tactics/TA0008/))
- Seeks to move through the network and jump to other targeted systems
- Using credentials and elevated privileges
- Stealthier the technique the better
## Phase: Out (Action of Objectives)
- Wraps up the journey of an adversary's attack on an environment
- They have critical asset access and can achieve goals
- Goals are usually towards compromising CIA
### Collection ([MITRE Tactic TA0009](https://attack.mitre.org/tactics/TA0009/))
- Gather all valuable data of interest
- Compromising confidentiality of data
- Sources include: drives, browsers, audio, video and email
### Exfiltration ([MITRE Tactic TA0010](https://attack.mitre.org/tactics/TA0010/))
- Seek to steal data
- Packaged using encryption measures and compression to avoid detection
- C2 channel and tunnel deployed early will help this process
### Impact ([MITRE Tactic TA0040](https://attack.mitre.org/tactics/TA0040/))
- Compromise integrity and availability of the data assets
- Manipulate, interrupt or destroy these assets
- Goal would be to disrupt business and operational processes by removing account access, disk wipes, data encryption, defacement, DoS attacks
### Objectives
- With access to systems and network, adversary would seek to achieve their strategic goal for the attack
## Practical
- The Attacker uses tools to gather information about the system: What phase of the Unified Kill Chain is this?
	- Reconnaissance 
- The Attacker installs a malicious script to allow them remote access at a later data: What phase of the UKC is this?
	- Persistence
- The hacked machine is being controlled from an Attacker's own server: What phase of the UKC is this?
	- Command and Control
- The Attacker uses the hacked machine to access other servers on the same network: What phase of the UKC is this?
	- Pivoting
- The Attacker steals a database and sells this to a 3rd party: What phase of the UKC is this?
	- Action and Objectives