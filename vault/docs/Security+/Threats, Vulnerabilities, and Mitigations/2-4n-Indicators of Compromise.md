# 2.4n - Indicators of Compromise
## IOC (Indicators of Compromise)
- An event that indicates an intrusion
	- Confidence is high
- Indicators
	- Unusual amount of network activity
	- Change to file hash values
	- Irregular international traffic
	- Changes to DNS data
	- Uncommon login patterns
	- Spikes of read requests to certain files
## Account lockout
- Credentials are not working
	- It wasn't you this time
- Exceeded login attempts
	- Account was administratively locked
- Account was administratively disabled
	- Attacker locks account
	- Calls support line to rest the password
## Concurrent session usage
- It's challenging to be two places at one time
- Multiple account logins from multiple locations
	- Interactive access from a single user
- This can be difficult to track down
	- Multiple devices and desktops
	- Automated processes
## Blocked content
- An attacker wants to stay as long as possible
	- Your system has been unlocked
	- Keep the system unlocked for future use
- There's probably a security patch available
	- Time to play keep-away
- Blocked content
	- Auto-update connections
	- Links to security patches
	- Third-party anti-malware sites
	- Removal tools
## Impossible
- Authentication logs can be telling
	- Logon and logoff
- Login from one location, 3 minutes later login from somewhere else
	- Impossible travel - involves detecting login attempts from locations that are geographically inconsistent or implausible suggesting that an attacker has compromised the user credentials
- This should be easy to identify
	- Log analysis and automation
## Resource consumption
- Every attacker's action has an equal and opposite reaction
	- Watch carefully for significant changes
- File transfers use bandwidth
	- An unusual spike at 3 AM
- Firewall logs show the outgoing transfer
	- IP addresses, timeframes
- Often the first real notification of an issue
	- The attacker may have been here for months
	- Resource inaccessibility
- The server is down - not responding
- Network disruption - A cover for actual exploit
- Server outage - A potential ransomware attack begins
- Brute force attacker - locks account access
## Out-of-cycle logging
- Out-of-cycle - occurs at an unexpected time
- Operating system patch logs
	- Occurring outside of the normal patch day
	- Keep that exploited system safe from other attackers!
- Firewall log activity
	- Timestamps of every traffic flow
	- Protocols and applications used
## Missing logs
- Log information is evidence
	- Attackers will try to cover their tracks by removing logs
- Information is everywhere
	- Authentication logs
	- File access logs
	- Firewall logs
	- Proxy logs
	- Server logs
- The logs may be incrimintating
	- Missing logs are certainly suspicious
	- Logs should be secured and monitored
## Published/Documented
- The entire attack and data exfiltration may go unnoticed
	- It happens quite often
- Company data may be published online
- The attackers post a portion or all data
	- This may be in conjunction with ransomware
- Raw data may be released without context
	- Researchers will try to find the source