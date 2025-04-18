# 4.8a - Incident Response
## Security incidents
- User clicks an email attachment and executes malware
	- Malware then communicates with external servers
- DDoS
	- Botnet attack
- Confidential information is stolen
	- Thief wants money or it goes public
- User installs peer-to-peer software and allows external access to internal servers
## NIST SP800-61
- National Institute of Standards and Technology
	- NIST Special Publication 800-61 Revision 2
	- Computer Security Incident Handling Guide
- The incident response lifecycle:
	- Preparation
	- Detection and Analysis
	- Containment, Eradication and Recovery
	- Post-incident Activity
## Preparing for an incident
- Communication methods
	- Phones and contact information
- Incident handling hardware and software
	- Laptops, removable media, forensic software, digital cameras, etc
- Incident analysis resources
	- Documentation, network diagrams, baselines, critical file hash values
- Incident mitigation software
	- Clean OS and application images
- Policies needed for incident handling
	- Everyone knows what to do 
## The challenge of detection
- Many different detection sources
	- Different levels of detail, different levels of perception
- A large amount of "volume"
	- Attacks are incoming all the time
	- How do you identify the legitimate threats?
- Incidents are almost always complex
	- Extensive knowledge needed
	- Analysis
- An incident might occur in the future
- Web server log
	- Vulnerability scanner in use
- Exploit announcement
	- Monthly Microsoft patch release, Adobe flash update
- Direct threats
## Analysis
- An attack is underway - or an exploit is successful
- Buffer overflow attempt
	- Identified by an intrusion detection / prevention system
- Anti-virus software identifies malware
	- Deletes from OS and notifies administrator
- Host-based monitor detects configuration change
	- Constantly monitoring system files
- Network traffic flows deviate from the norm
	- Require constant monitoring
## Isolation and containment
- Generally a bad idea to let things run their course
	- An incident can spread quickly
	- It's your fault at that point
- Sandboxes
	- An isolated operating system
	- Run malware and analyze the results
	- Clean out the sandbox when done
- Isolation can be sometimes problematic
	- Malware or infections can monitor connectivity
	- When connectivity is lost, everything could be deleted/encrypted/damaged
## Recovery after an incident
- Get things back to normal
	- Remove the bad, keep the good
- Eradicate the bug
	- Remove malware
	- Disable breached user accounts
	- Fix vulnerabilities
- Recover the system
	- Restore from backups
	- Rebuild from scratch
	- Replace compromised files
	- Tighten down the perimeter
## Lessons learned
- Learn and improve
	- No system is perfect
- Post-incident meeting
	- Invite everyone affected by the incident
- Don't wait too long
	- Memories fade over time
	- Some recommendations can be applied to the next event
## Answer the tough questions
- What happened, exactly?
	- Timestamp of the events
- How did you incident plans work?
	- Did the process operate successfully?
- What would you do differently next time?
	- Retrospective views provide context
- Which indicators would you watch next time?
	- Different precursors may give you better alerts
## Training for an incident
- There's limited on-the-job training when a security event occurs
	- Be ready when an incident is identified
- Train the team prior to an incident
	- Initial response
	- Investigation plans
	- Incident reporting
	- And more
- This can be more expensive endeavor
	- Especially with larger response teams