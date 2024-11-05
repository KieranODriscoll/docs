# 1.2 - Threat Intelligence Tools
## Threat Intelligence
- analysis of data and information using tools and techniques to generate meaningful patterns on how to mitigate against potential risks
- Answer following questions to start:
	- Who's attacking you?
	- What's their motivation?
	- What are their capabilities?
	- What artefacts and indicators of comprise should you look out for?
## Threat Intelligence Classifications
- Threat intel is geared towards understanding the relationship between your operational environment and your adversary
- Classifications:
	- **Strategic Intel**: High-level intel that looks into the organization's threat landscape and maps out the risk areas based on trends, patterns and emerging threats that may impact business decisions
	- **Technical Intel**: Looks into evidence and artefacts of attack used by an adversary. Incident Response teams can use this intel to create a baseline attack surface to analyze and develop defense mechanisms
	- **Tactical Intel**: Assesses adversaries' tactics, techniques, and procedures (TTPs). This intel can strengthen security controls and address vulnerabilities through real-time investigations
	- **Operational Intel**: Looks into adversary's specific motives and intent to perform an attack. Security teams may use this intel to understand the critical assets available in the organization (people, processes, and technologies) that may be targeted
## Urlscan.io
- free service developed to assist in scanning and analyzing websites.
- Automates the process of browsing and crawling through websites to record activities and interactions
- Scan Results
	- Summary - Provides general information about the URL
	- HTTP - Provides information on the HTTP connections, data fetched and the files types received
	- Redirects - Shows information on any identified HYYP and client-side redirects on the site
	- Links - Shows all the identified links outgoing from the site's homepage
	- Behaviour - Provides details of the variables and cookies found on the site
	- Indicators - Lists all IPs, domains and hashes associated with the site. 
## Abuse.ch
- Developed to identify and track malware and botnets through several operational platforms developed under the project. These platforms are:
	- Malware Bazaar - A resource for sharing malware samples
	- Feodo Tracker - A resource used to track botnet command and control (C2) infrastructure linked with Emotet, Dirdex and Trickbot
	- SSL Blacklist - A resource for collecting and providing a blocklist for malicious SSL certificates and JA3/JA3s fingerprints
	- URL Haus - A resource for sharing malware distribution sites
	- Threat fox - A resource for sharing indicators of compromise (IOCs)
## PhishTool
- Seeks to elevate the perception of phishing as a severe form of attack and provide a responsive means of email security.
- Email analysis helps analysts uncover email IOCs, prevent breaches and provide forensic reports that could be used in phishing containment and training engagements
- Core Features:
	- **Perform email analysis** - retrieves metadata from phishing emails and provides analysts with the relevant explanations and capabilities to follow the email's actions, attachments and URLs to triage.
	- **Heuristic intelligence** - OSINT is backed into the tool to provide analysts with the intelligence needed to stay ahead of persistent attacks and understand what TTPs were used to evade security controls and allow the adversary to social engineer a target.
	- **Classification and Reporting** - Phishing email classifications are conducted to allow analysts to take action quickly. Additionally, reports can be generated to provide forensic record that can be shared.
## Cisco Talos
- Provides actionable intelligence, visibility on indicators and protection against emerging threats through data collected from their products.
- Encompasses six key terms:
	- **Threat Intelligence & Interdiction** - Quick correlation and tracking of threats provide a means to turn simple IOCs into context-rich intel
	- **Detection Research** - Vulnerability and malware analysis is performed to created rules and content for threat detection
	- **Engineering & Development** - Provides the maintenance support for the inspection engines and keeps them up-to-date to identify and triage emerging threats
	- **Vulnerability Research & Discovery** - Working with service and software vendors to develop repeatable means of identifying and reporting security vulnerabilities
	- **Communities** - Maintains the image of the team and the open-source solutions
	- **Global Outreach** - Disseminates intelligence to customers and the security community through publications