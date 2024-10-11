# 1.1 - Introduction to Cyber Threat Intelligence
## Cyber Threat Intelligence
- Defined as evidence-based knowledge about adversaries including their indicators, tactics, motivations, and actionable advice against them
- Utilized to protect critical assets and inform cyber security teams and management business decisions
- **Data** - Discrete indicators associated with an adversary, such as IP, URLs, or hashes
- **Information** - A combination of multiple data points that answer questions such as "How many times have employees accessed \<site\> within the month"
- **Intelligence** - The correlation of data and information to extract patterns of actions based on contextual analysis
- Primary goal of CTI is to understand the relationship between your operational environment and your adversary and how to defend your environment against attacks
- Seek this goal by developing your cyber threat context by answering the following questions:
	- Who's attacking?
	- What are their motivations?
	- What are their capabilities?
	- What artifacts and IOCs should you look out for?
- Threat intelligence can be gathered from different sources in the following categories:
	- **Internal**
		- Corporate security events such as vulnerability assessments and incident response reports
		- Cyber awareness training reports
		- System logs and events
	- **Community**
		- Open web forums
		- Dark web communities for cybercriminals
	- **External**
		- Threat intel feeds (Commercial & Open-source)
		- Online marketplaces
		- Public sources including government data, publications, social media, financial and industrial assessments
### Threat Intelligence Classifications
- **Strategic Intel** - High-level intel that looks into the organization's threat landscape and maps out the risk areas based on trends, patterns and emerging threats that may impact business decisions
- **Technical Intel** - Looks into evidence and artefacts of attack used by an adversary. Incident Response teams can use this intel to create a baseline attack surface to analyze and develop defense mechanisms
- **Tactical Intel** - Assesses adversaries' tactics, techniques, and procedures (TTPs). This intel can strengthen security controls and address vulnerabilities through real-time investigations
- **Operational Intel** - Looks into an adversary's specific motives and intent to perform an attack. Security teams may use this intel to understand the critical assets available in the organization (people, processes and technologies) that may be targeted
## CTI Lifecycle
- Threat into is a data-churning process that transforms raw data into contextualized and action-oriented insights geared towards triaging security incidents
- Transformational process follows a six-phase cycle:
![Pasted_image_20241011153730](//assets/Pasted_image_20241011153730.webp)
### Direction
- Objectives and goals defined with the following parameters
	- Information assets and business processes that require defending
	- Potential impact to be experienced on losing the assets or through process interruptions
	- Sources of data and intel to be used toward protection
	- Tools and resources that are required to defend the assets
- Allows security analysts to pose questions related to investigating incidents
### Collection
- Gather the required data to address the defined objectives
- Collected using commercial, private or open-source available
- Since the volume of data analysts usually face, recommended to automate this phase to provide time for triaging incidents
### Processing
- Raw logs, vulnerability information, malware and network traffic usually comes in different forms and may be disconnected when used to investigate an incident
- Ensures that the data is extracted, sorted, organized, correlated with appropriate tags
- Presented visually in an understandable format
- SIEMs are valuable tools for achieving this and allowing quick parsing of data
### Analysis
- Decisions to be made may involve:
	- Investigating a potential threat through uncovering indicators and attack patterns
	- Defining an action plan to avert an attack and defend the infrastructure
	- Strengthening security controls or justifying investment for additional resources
### Dissemination
- Different stakeholders will consume the intelligence in varying languages and formats
- C-suite will want a concise report covering trends in adversary activitions, etc
- Analysts will want to inform technical team of threat IOCs, adversary TTPs, tactical action plans, etc
### Feedback
- Final face, most crucial
- Feedback from stakeholders to improve the threat intelligence process and implementation of security controls
- Feedback should be regular interaction between teams to keep lifecycle working
# CTI Standards & Frameworks
### MITRE ATT&CK
- knowledge base of adversary behaviour, focusing on the indicators and tactics
- Information to be thorough while investigating and tracking adversarial behaviour
### TAXII
- [The Trusted Automated eXchange of Indicator Information (TAXII)](https://oasis-open.github.io/cti-documentation/taxii/intro) defines protocols for securely exchanging threat intel to have near real-time detection, prevention and mitigation of threats
	- **Collection** - threat intel is collected and hosted by a producer upon request by users using a request-response model
	- **Channel** - threat intel is pushed to users from a central server through a publish-subscribe model
### STIX
- [Structured Threat Information Expression (STIX)](https://oasis-open.github.io/cti-documentation/stix/intro) is a language developed for "specification, capture, characteristics and communication of standardized cyber threat information"
- Provides relationships between sets of threat info such as observables, indicators, adversary TTPs, attack campaigns and more
### Cyber Kill Chain
- Breaks down adversary actions into steps
![Pasted_image_20241011155940](//assets/Pasted_image_20241011155940.webp)
- More information can be found here [1-3-Cyber-Kill-Chain](https://docs.kodriscoll.xyz/TryHackMe/SOC%20Level%201/Cyber%20Defense%20Frameworks/1-3-Cyber-Kill-Chain)
