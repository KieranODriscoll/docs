# 4.8 - Log Data
## Security log files
- Detailed security-related information
	- Blocked and allowed traffic flows
	- Exploit attempts
	- Blocked URL categories
	- DNS sinkhole traffic
- Critical security information
	- Documentation of every traffic flow
	- Summary of attack info
	- Correlated with other logs
## Firewall Logs
- Traffic flows through the firewall
	- Source/Destination IP, port number, disposition
- Next Generation Firewall (NGFW)
	- Logs the application used, URL filtering categories, anomalies, and suspicious data
## Application logs
- Specific to the application
	- Information varies widely
- Windows
	- Event Viewer / Application Log
- Linux / MacOS
	- var/log
	- Parse the log details on the SIEM
		- Filter out unneeded info
## Endpoint logs
- Attackers often gain access to endpoints
	- Phones, laptops, tablets, desktops, servers, etc
- There's a lot of data on the endpoint
	- Logon events, policy changes, system events, processes, account management, directory services, etc
- Everything rolls up to the SIEM
	- Security Information and Event Manager
- Use with correlation of security events
	- Combine IPS events with endpoint status
## OS-specific Security lgos
- OS security events
	- Monitoring apps
	- Brute force, file changes
	- Authentication details
- Find problems before they happen
	- Brute force attacks
	- Disabled services
- May require filtering
	- Don't forward everything
## IPS/IDS logs
- Intrusion prevention system / intrusion detection system
	- Usually integrated into an NGFW
- Logs contain information about predefined vulnerabilities
	- Known OS vulnerabilities, generic security events
- Common data points
	- Timestamp
	- Type or class of attack
	- Source and destination IP
	- Source and destination port
## Network logs
- Switches, routers, access points, VPN concentrators, other infrastructure devices
- Network changes
	- Routing updates
	- Authentication issues
	- Network security issues
## Metadata
- Data that describes other data sources
- Email
	- Header details, sending services, destination address
- Mobile
	- Type of phone, GPS location
- Web
	- Operating system, browser type, IP address
- Files
	- Names, address, phone number, title
## Vulnerability scans
- Lack of security controls
	- No firewall
	- No anti-virus
	- No anti-spyware
- Misconfigurations
	- Open shares
	- Guest access
- Real vulnerabilities
	- Especially newer ones
	- Occasionally the old ones
## Automated reports
- Most SIEMs include a report generator
	- Automate common security reports
- May be easy or complex to create
	- The SIEM may have its own report generator
	- Third-part report generators may be able to access the database
- Requires human intervention
	- Someone has to read the reports
- These can be involved to create huge data storage and extensive processing time
## Dashboards
- Real-time status information
	- Get summaries on a single screen
- Adds or remove information
	- Most SIEMs and reporting systems allow for customization
- Shows the most important data
	- Not designed for long-term analysis
## Packet captures
- Solve complex application issues
	- Get into the details
- Gather packets on the network
	- Or in the air
	- Sometimes built into the device
- View detailed traffic information
	- Identify unknown traffic
	- Verify packet filtering and security controls
	- View a plain-language description of application data