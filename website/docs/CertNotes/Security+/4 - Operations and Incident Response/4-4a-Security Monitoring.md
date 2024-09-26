# 4.4a - Security Monitoring
## Security monitoring
- The attackers never sleep - 24/7/365
- Monitor all entry points
	- Logins, publicly available services, data storage locations, remote access
- React to security events
	- Account access, firewall rule base, additional scanning
- Status dashboards
	- Get the status of all systems at a glance
## Monitoring computing resources
- Systems
	- Authentication - logins from strange places
	- Server monitoring - Service activity, backups, software versions
- Applications
	- Availability - Uptime and response times
	- Data transfers - increases or decreases in rates
	- Security notifications - From the developer/manufacturer
- Infrastructure
	- Remote access systems - Employees, vendors, guests
	- Firewall and IPS reports - Increase or type of attack
## Log aggregation
- SIEM or SEM (Security Information and Event Manager)
	- Consolidate many different logs to a central database
	- Severs, firewalls, VPN concentrators, SANs, cloud services
- Centralized reporting
	- All information in one place
- Correlation between diverse systems
	- View authentication and access
	- Track application access
	- Measure and report on data transfers
## Scanning
- A constantly changing threat landscape
	- New vulnerabilities discovered daily
	- Many different business applications and services
	- Systems and people are always moving
- Actively check systems and devices
	- Operating system types and versions
	- Device driver versions
	- Installed applications
	- Potential anomalies
- Gather the raw details
	- A valuable database of information
## Reporting
- Analyze the collected data
	- Create "actionable" reports
- Status information
	- Number of devices up to date/in compliance
	- Devices running older operating systems
- Determine best next steps
	- A vulnerability is announced
	- How many systems are vulnerable?
- Ad hoc information summaries
	- Prepare for the unknown
## Archiving
- It takes an average of about 9 months for a company to identify and contain a breach
	- IBM security report, 2022
- Access to data is critical
	- Archive over an extended period
- May have a mandate
	- State or federal law
	- Or organizational requirements
## Alerting
- Real-time notification of security events
	- Increase in authentication errors
	- Large file transfers
- Actionable data
	- Keep the right people informed
	- Enable quick response and status information
- Notification methods
	- SMS/text
	- Email
	- Security console / SOC
## Alert response and remediation
- Quarantine
	- A foundational security response
	- Prevent a potential security issue from spreading
	- When a file is quarantined, it is isolated, ensuring the user, or any possible user cannot access it. This is achieved by encrypting the file or moving it to a designated quarantine zone in the file system
- Alert tuning
	- A balancing act
	- Prevent false positives and false negatives
- An alert should be accurate
	- This is an ongoing process
	- The tuning gets better as time goes on
