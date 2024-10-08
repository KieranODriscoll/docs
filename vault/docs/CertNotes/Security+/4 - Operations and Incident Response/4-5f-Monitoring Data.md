# 4.5f - Monitoring Data
## FIM (File Integrity Monitoring)
- Some files change all the time
	- Some files should NEVER change
- Monitor important operating system and application files
	- Identify when changes occur
- Windows - SFC (System File Checker)
- Linux - Tripwire
- Many host-based IPS options
## Data Loss Prevention (DLP)
- Where's your data?
	- SSN, credit cards, medical records
- Stop the data before the attackers get it
	- Data "leakage"
- So many sources, so many destinations
	- Often requires multiple solutions in different places
## DLP Systems
- On your computer
	- Data in use
	- Endpoint DLP
- On your network
	- Data in motion
- On your server
	- Data at rest
## USB blocking
- DLP on a workstation
	- Allow or deny certain tasks
- November 2008 - US DoD
	- Worm virus "agent.btz" replicates using USB storage
	- Bans removable flash media and storage devices
- All devices had to be updated
	- Local DLP agent handled USB blocking
- Ban was lifted in February 2010
	- Replaced with strict guidelines
## Cloud-based DLP
- Located between users and the Internet
	- Watch every byte of network traffic
	- No hardware, no software
- Blocked custom defined data strings
	- Unique data for your organization
- Manage access to URLs
	- Prevent file transfers to cloud storage
- Block viruses and malware
	- Anything traversing the network
## DLP and email
- Email continues to be the most critical risk vector
	- Inbound threats, outbound data loss
- Check every email inbound and outbound
	- Internal system or cloud-bgased
- Inbound
	- Block keywords, identify impostors, quarantine email messages
- Outbound
	- Fake wire transfers, W-2 transmissions, employee information
## Emailing a spreadsheet template
- November 2016
- Boeing employee emails spouse a spreadsheet to use as a template
- Contained the personal information of 36,000 Boeing employees
	- In hidden columns
	- SSN, DoB, etc
- Boeing sells its own DLP software
	- But only uses it for classified work