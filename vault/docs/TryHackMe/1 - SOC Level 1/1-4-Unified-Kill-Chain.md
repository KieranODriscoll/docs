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