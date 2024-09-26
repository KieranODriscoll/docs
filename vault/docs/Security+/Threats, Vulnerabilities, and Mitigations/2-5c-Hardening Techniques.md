# 2.5c - Hardening Techniques
## System hardening
- Updates
	- Operating system updates/service packs, security patches
- User accounts
	- Minimum password lengths and complexity
	- Account limitations
- Network access and security
	- Limit network access
- Monitor and secure
	- Anti-virus, anti-malware
## Encryption
- Prevent access to application data files
	- File system encryption
	- Windows Encrypting File System (EFS)
- Full disk encryption (FDE)
	- Encrypt everything on the drive
- Encrypt all network communication
	- VPN
	- Application encryption
## The endpoint
- The user's access - Applications and data
- Stop the attackers - Inbound attacks, outbound attacks
- Many different platforms - Mobile, desktop
- Protection is multi-faceted - Defense in depth
## Endpoint detection and response (EDR)
- A different method of threat protection
	- Scale to meet the increasing number of threats
- Detect a threat
	- Signatures aren't the only detection tool
	- Behavioral analysis, machine learning, process monitoring
	- Lightweight agent on the endpoint
- Investigate the threat - Root cause analysis
- Respond to the threat
	- Isolate the system, quarantine the threat, rollback to a previous config
	- API driven, no user or technician intervention required
## Host-based firewall
- Software-based firewall
	- Personal firewall, runs on every endpoint
- Allow or disallow incoming or outgoing application traffic
	- Control by application process
	- View all data
- Identify and block unknown processes
	- Stop malware before it can start
- Manage centrally
## Finding intrusions
- Host-based intrusion
	- Prevention system (HIPS), Recognize and block known attacks
	- Secure OS and application configs, validate incoming service requests
	- Often built into endpoint protection software
- HIPS identification
	- Signatures, heuristics, behavioral
	- Buffer overflows, registry updates, writing files to the Windows folder
	- Access to non-encrypted data
## Open ports and services
- Every open port is a possible entry point
	- Close everything except required ports
- Control access with a firewall
	- NGFW would be ideal
- Unused or unknown services
	- Installed with the OS or from other applications
- Applications with broad port ranges
	- Open port 0 through 65,535
- Use nmap or similar port scanner to verify
	- Ongoing monitoring is important
## Default password changes
- Every network device has a management interface
	- Critical systems, other devices
- Many applications also have management or maintenance interfaces
	- Can contain sensitive data
- Change default settings
	- Passwords
- Add additional security
	- Require additional logon
	- Add 3rd-party authentication
## Removal of unnecessary software
- All software contains bugs
	- Some of those bugs are security vulnerabilities
- Every application seems to have a completely different patching process
	- Can be challenging to manage ongoing updates
- Remove all unused software
	- Reduce your risk
	- An easy fix