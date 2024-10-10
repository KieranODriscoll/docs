# Diamond Model
### Introduction
- Composed of 4 core features:
	- Adversary, infrastructure, capability, and victim
	- Establishes the fundamental atomic element of an intrusion activity
	- Two additional components or axes of the Diamond Model
		- Social
		- Political
		- Technology
- Four core features are edge-connected, representing their underlying relationships and arranged in the shape of a diamond
- Essential concepts of intrusion analysis and adversary operations while still allowing flexibility to expand and encompass new ideas and concepts
### Adversary
- Adversary is also known as an attacker, enemy, cyber threat actor, or hacker
- responsible for utilizing a capability against the victim to achieve their intent
- Difficult to identify an adversary during the first stages of a cyberattack
	- Data collected from incident or breach, signatures and other relevant information can help determine
- **Adversary Operator**
	- is the hacker or person conducting the intrusion activity
- **Adversary Customer**
	- the entity that stands to benefit from the activity conducted in the intrusion. Could be the Operator or a separate person or group
### Victim
- Victim is a target of the adversary. 
- Can be an organization, person, target email, IP address, domain, etc
- Victim could be an opportunity for the attackers to get a foothold they are trying ot attack
- Always a victim in every cyberattack
- **Victim Personae**
	- The people or organizations being target and whose assets are being attacked and exploited
	- Can be organization names, people's names, industries, job roles, interests, etc
- **Victim Assets**
	- Attack surface and include the set of systems, networks, email addresses, hosts, IP address, social networking accounts, etc
	- Adversary will direct their capabilities to these
### Capability
- Skill, tools and techniques used by the adversary
- Highlights the adversary's tactics, techniques and procedures (TTPs)
- Includes all techniques used to attack the victims from less sophisticated to most sophisticated
- **Capability Capacity** 
	- all of the vulnerabilities and exposures that the individual capability can use
- **Adversary Arsenal**
	- set of capabilities that belong to an adversary. Combined capacities of an adversary's capabilities make the adversary's arsenal
### Infrastructure
- Known as software and hardware
- Physical or logical interconnections that the adversary uses to deliver a capability or maintain control of capabilities.
	- Example: Command and control centre (C2) and the results from the victim (data exfiltration)
- Can also include IP addresses, domain names, email addresses, or even a malicious USB device plugged into a workstation
- **Type 1 Infrastructure**
	- Infrastructure controlled or owned by the adversary
- **Type 2 Infrastructure**
	- infrastructure controlled by an intermediary
	- Intermediary may or may not be aware of it
	- Infrastructure a victim will see as the adversary
	- Purpose of obfuscating the source and attribution of the activity
	- Includes malware staging servers, malicious domain names, compromised email addresses, etc
- **Service Providers**
	- Organizations that provide services considered critical to adversary availability of Type 1 and Type 2 infrastructure. Ex. ISP, Domain registrars and webmail providers
### Event Meta Features
- Six possible meta features can be added to the Diamond Model
- Meta features are not required but can add some valuable information or intelligence
- Features:
	- **Timestamp**
		- Date and time of the event
		- Can be start and stop time of the eventt
		- Essential for determining patterns and group the malicious data
	- **Phase**
		- Phases of an intrusion, attack, or breach
		- "Every malicious activity contains two or more phases which must be successfully executed in succession to achieve desired results"
		- Phases can be from one of the many Kill Chains
	- **Result**
		- Results and post-conditions of adversary's operations will not always be known or have a high confidence value when they are known. Still helpful to capture
		- Event results can be labelled as success, failure, unknown
		- Can also be related to CIA compromise
		- Can also be documenting the post-conditions of the event such as: information gathered, data exfiltration
	- **Direction**
		- Helps describe host-based and network-based events and represents the direction of the intrusion
		- Potential values: Victim-to-infrastructure, Infrastructure-to-victim, Infra-to-Infra, Adversary-to-infra, Infra-to-Adversary, Bidirectional or unknown
	- **Methodology**
		- Allow an analyst to describe the general classification of intrusion. Ex. DDos, Phishing, etc
	- **Resources**
		- Every intrusion event needs one or more external resources to be satisfied to succeed
		- **Software** (OS, Metasploit framework, etc), **Knowledge** (How to use tools, etc), **Information** (Credentials, etc), **Hardware** (Servers, workstations, routers, etc), **Funds** (Money to purchase domains, etc), **Facilities** (Electricity, shelter, etc), **Access** (Network path from source host to victim or vice versa, network access from ISP, etc)
### Social-Political Component
- Describes the needs and intent of the adversary.
- Financial gain, gaining acceptance in hacker community, espionage
- Scenario can be that the victim provides a "product": computing resources & bandwidth as a zombie in a botnet for crypto mining purposes
### Technology Component
- Highlights the relationship between the core features: Capability and Infrastructure
- Describes how the adversary operates and communicates
- Scenario can be a watering-hole attack