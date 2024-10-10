# MITRE
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
![Pasted_image_20241010134641](//assets/Pasted_image_20241010134641.webp)
- [ATT&CK Navigator](https://mitre-attack.github.io/attack-navigator//#layerURL=https%3A%2F%2Fattack.mitre.org%2Fgroups%2FG0008%2FG0008-enterprise-layer.json) helps map TTPs
## CAR Knowledge Base
- [Cyber Analytics Repository](https://car.mitre.org/)
- Knowledge base of analytics developed by MITRE based on the ATT&CK adversary Model. "Defines a data model that is leveraged in its pseudocode representations but also includes implementation directly targeted at specific tools (eg. Splunk, EQL (Event Query Language)) in its analytics. Focused on providing a set of validated and well-explained analytics, in particular with regards to their operating theory and rationale"
### Example
- [CAR-2020-09-001: Scheduled Task - File Access](https://car.mitre.org/analytics/CAR-2020-09-001/)
![Pasted_image_20241010135723](//assets/Pasted_image_20241010135723.webp)
- Provided with Pseudocode and a query on how to search for this specific analytic within Splunk
![Pasted_image_20241010135804](//assets/Pasted_image_20241010135804.webp)
- To take full advantage of CAR, [Full Analytic List](https://car.mitre.org/analytics) or the [CAR ATT&CK® Navigator layer](https://mitre-attack.github.io/attack-navigator/#layerURL=https://raw.githubusercontent.com/mitre-attack/car/master/docs/coverage/car_analytic_coverage_04_05_2022.json) to view all the analytics.
