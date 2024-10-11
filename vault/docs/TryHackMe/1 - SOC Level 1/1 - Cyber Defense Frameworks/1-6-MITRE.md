# 1.6 - MITRE
## Basic Terminology
- **APT**
	- Advanced Persistent Threat
	- Considered a team/group (threat group) or even country (nation-state group), that engages in long-term attacks against organizations and/or countries
	- "Advanced" can be misleading as it will tend to cause us to believe APT have some super-weapon (ie. zero-days) that they use. That is not always the case.
- **Tactics, Techniques, and Procedures**
	- **Tactic** - adversary's goal or objective
	- **Technique** - how the adversary achieves the goals or objective
	- **Procedure** - how the technique is executed
### ATT&CK Framework
- Globally-accessible knowledge base of adversary tactics and techniques based on real-world observations
- MITRE began documenting common TTPs that APT groups used. Originally started as an internal project known as FMX. Security professionals were tasked to emulated adversarial TTPs against a network and data was collected from the attacks, beginning what is known as the ATT&CK Framework
- Covers Windows, Mac and Lianux
- Consists of 14 categories (taken from the Unified Kill Chain) which cover the seven-stage Cyber Attack Lifecycle from the Cyber Kill Chain
- Each category has techniques under it, with sub-techniques within them
- Example: Phishing for initial access
	- ![](assets/Pasted%20image%2020241010134641.png)
- [ATT&CK Navigator](https://mitre-attack.github.io/attack-navigator//#layerURL=https%3A%2F%2Fattack.mitre.org%2Fgroups%2FG0008%2FG0008-enterprise-layer.json) helps map TTPs
## CAR Knowledge Base
- [Cyber Analytics Repository](https://car.mitre.org/)
- Knowledge base of analytics developed by MITRE based on the ATT&CK adversary Model. "Defines a data model that is leveraged in its pseudocode representations but also includes implementation directly targeted at specific tools (eg. Splunk, EQL (Event Query Language)) in its analytics. Focused on providing a set of validated and well-explained analytics, in particular with regards to their operating theory and rationale"
### Example
- [CAR-2020-09-001: Scheduled Task - File Access](https://car.mitre.org/analytics/CAR-2020-09-001/)
- ![](assets/Pasted%20image%2020241010135723.png)
- Provided with Pseudocode and a query on how to search for this specific analytic within Splunk
- ![](assets/Pasted%20image%2020241010135804.png)
- To take full advantage of CAR, [Full Analytic List](https://car.mitre.org/analytics) or the [CAR ATT&CK® Navigator layer](https://mitre-attack.github.io/attack-navigator/#layerURL=https://raw.githubusercontent.com/mitre-attack/car/master/docs/coverage/car_analytic_coverage_04_05_2022.json) to view all the analytics.
## MITRE Engage
- [MITRE ENGAGE](https://engage.mitre.org/)
- "Framework for planning and discussing adversary engagement operations that empowers you to engage your adversaries and achieve your cybersecurity goals"
- Considered an **Adversary Engagement Approach** accomplished by the implementation of **Cyber Denial** and **Cyber Deception**
	- **Cyber Denial** - prevent the adversary's ability to conduct their operations
	- **Cyber Deception** - intentionally plant artifacts to mislead the adversary
### Engage Matrix
- ![](assets/Pasted%20image%2020241010141314.png)
- **Prepare** - set of operational actions that will lead to your desired outcome (input)
- **Expose** - adversaries when they trigger your deployed deception activities
- **Affect** - adversaries by performing actions that will have a negative impact on their operations
- **Elicit** - information by observing the adversary and learn more about their modus operandi (TTPs)
- **Understand** - outcomes of the operational actions (output)
- [Engage Matrix Explorer](https://engage.mitre.org/matrix)
## MITRE D3FEND
- [D3FEND](https://d3fend.mitre.org/)
- A knowledge graph of cybersecurity countermeasures
- Detection, Denial, Disruption Framework Empowering Network Defense
- Provides information on what is the technique, how the technique works, things to think about when implementing and how to utilize the technique
## ATT&CK Emulation Plans
- [MITRE ENGENUITY](https://mitre-engenuity.org/)
	- CTID, the Adversary Emulation Library and ATT&CK Emulation Plans
### CTID
- Center of Threat-informed Defense
- Consists of various companies and vendors around the globe
- Conduct research on cyber threats and their TTPs and share this research
### Adversary Emulation Library & ATT&CK Emulation Plans
- [Adversary Emulation Library](https://mitre-engenuity.org/cybersecurity/center-for-threat-informed-defense/adversary-emulation-library/) is a public library making adversary emulation plans a free resource
- Emulation plans are step-by-step guide on how to mimic the specific threat group
## ATT&CK and Threat Intelligence
- **Threat Intelligence (TI)** or **Cyber Threat Intelligence (CTI)** is information or TTPs attributed to the adversary
- By using TI, defenders, can make better decisions regarding the defensive strategy
- Goal of threat intelligence is to make the information actionable
