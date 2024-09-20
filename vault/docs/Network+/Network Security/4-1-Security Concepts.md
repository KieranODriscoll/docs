# 4.1 - Security Concepts
## CIA Triad
- Combination of principles
	- The fundamentals of security
- Confidentiality
	- Prevent disclosure of information to unauthorized individuals or systems
- Integrity
	- Messages can't be modified without detection
- Availability
	- Systems and networks must be up and running
### Confidentiality
- Certain information should only be known to certain people
- Encryption
	- Encode messages so only certain people can read it
- Access controls
	- Selectively restrict access to a resource
- Steganography
	- Conceal information within another piece of information
	- Commonly associated with hiding information in an image
### Integrity
- Data is stored and transferred as intended
	- Any modification to the data would be identified
- Hashing
	- Map data of an arbitrary length to data of a fixed length
- Digital Signatures
	- Mathematical scheme to verify the integrity of data
	- Provides authenticity of data
- Certificates
	- Combine with a digital signature to verify an individual
- Non-repudiation
	- Provides proof of integrity, can be asserted to be genuine
### Availability
- Information is accessible to authorized users
	- Always at your fingertips
- Redundancy
	- Build services that will always be available
- Fault tolerance
	- System will continue to run, even when a failure occurs
- Patching
	- Stability
	- Close security holes
## Security Concepts
### Vulnerabilities
- A weakness in a system
	- Allows the bad guys to gain access or cause a security breach
- Some vulnerabilities are never discovered
	- Or discovered after years of use
- Many different vulnerability types
	- Data injection
	- Broken authentication process
	- Sensitive data exposure
	- Security misconfiguration
### Zero-day attacks
- Many applications have vulnerabilities
	- We've just not found them yet
- Someone is working hard to find the next big vulnerability
	- The good guys share these with the developer
- Attackers keep these yet-to-be-discovered holes to themselves
- Zero-day
	- The vulnerability has not been detected or published
	- Zero-day exploits are increasingly common
- Common Vulnerabilities and Exposures (CVE)
### Threat
- A vulnerability can be exploited by a threat
	- May be intentional (attacker) or accidental (fire, floot)
	- Many of these threats are external to the organization
- A resource can have a vulnerability
	- The vulnerability can be exploited by a threat agent
	- The threat agent takes a threat action to exploit the vulnerability
- The result is a loss of security
	- data breach, system failure, data theft
### Insider Threats
- We give people tons of access
	- Least privilege, anyone
- You have more access than others just by entering the building
	- Lock away your documents
	- Some organizations have very specific procedures
- Significant security issues
	- Harms reputation
	- Critical system disruption
	- Loss of confidential or proprietary information
### Vulnerability databases
- Researchers find vulnerabilities
	- Everyone needs to know about them
- Common Vulnerabilities and Exposures (CVE)
	- A community managed list of vulnerabilities
	- Sponsored by the US Department of Homeland Security and Cybersecurity and Infrastructure Security Agency
- US National Vulnerability Data (NVD)
	- A summary of CVEs
- NVD provides additional details over the CVE list
	- Patch availability and severity scoring
### Exploits
- Take advantage of a vulnerability
	- Gain control of a system, modify data, disable a service
- Many exploit methods
	- Build to take advantage of a vulnerability
	- May be complex
### Least Privilege
- Rights and permissions should be set to the bare minimum
	- You only get exactly what's needed to complete your objective
- All user accounts must be limited
	- Applications should run with minimal privileges
- Don't allow users to run with administrative privileges
	- Limits the scope of malicious behavior
### Role-based access control
- You have a role in your organization
	- Manager, director, team lead, etc
- Administrators provide access based on the role of the user
	- Rights are gained implicitly instead of explicitly
- In Windows, use Groups to provide role-based access control
	- You are in shipping and receiving, so you can use shipping software
### Zero Trust
- Many networks are relatively open on the inside
	- Once you're through the firewall, there are few security controls
- Zero trust is a holistic approach to network security
	- Covers every device, every process, every person
- Everything must be verified
	- Nothing is trusted
	- Multifactor authentication, encryption, system permissions, additional firewalls, monitoring and analytics, etc
## Defense in Depth
### Layering the Defense
- Physical controls
	- Keep people away from the technology
	- Door locks, fences, rack locks, cameras
- Technical controls
	- Hardware and software to keep things secure
	- Firewalls, active directory authentication, disk encryption
- Administrative controls
	- Policies and procedures
	- Onboarding and offboarding
	- Backup media handling
### Defense in Depth
- Firewall
- Screened Subnet
- Hashing and salting passwords
- Authentication
- Intrusion prevention system
- VPN access
- Card/badge access
- Anti-virus and anti-malware software
- Security guard
### Physical Segmentation
- Separate devices
	- Multiple units, separate infrastructure
### Logical segmentation with VLANs
- Virtual Local Area Networks (VLANs)
	- Separate logically instead of physically
	- Cannon communicate between VLANs without a Layer 3 device / router
### Screened subnet
- Previously known as the demilitarized zone (DMZ)
	- An additional layer of security between the Internet and you
	- Public access to public resources
- is a physical or logical subnetwork that contains and exposes an organization's external-facing services to an untrusted network such as the internet
### Separation of Duties
- Split knowledge
	- No one person has all the details
	- Half of a safe combination
- Dual control
	- Two people must be present to perform the business function
	- Two keys open a safe
### Network Access Control (NAC)
- IEEE 802.1X - Port-based Network Access Control (NAC)
	- You don't get to access until you authenticate
- We're talking about physical interfaces
	- Not TCP or UDP ports
- Makes extensive use of EAP and RADIUS
	- Extensible Authentication Protocol / Remote Authentication Dial in User Services
- Administrative enable/disable
- Duplicate MAC address checking
	- Stop the spoofers
### Honeypots
- Attract the bad guys - and trap them there
- The "attacker" is probably a machine
	- Makes for interesting recon
- Honeypots - create a virtual world to explore
- Many different options
	- Kippo, Google Hack Honeypot, Wordpot, etc
- Constant battle to discern the real from the fake

## Authentication Methods
### Local Authentication
- Authentication credentials are stored on the local device
	- Must be individually administered
- Very manual process
	- A password change must be done manually on all devices
- Doesn't reply on a third-party authentication server
	- A network outage won't impact the login process
### Multi-factor authentication
- More than one factor
	- Something you are
	- Something you have
	- Something you know
	- Somewhere you are
	- Something you do
- Can be expensive
	- Separate hardware tokens
	- Specialized scanning equipment
- Can be inexpensive - free smartphone applications
### RADIUS (Remote Authentication Dial-in User Service)
- One of the more common AAA protocols
	- Supported on a wide variety of platforms and devices
	- Not just for dial-in
- Centralized authentication for users
	- Routers, switches, firewalls
	- Server authentication
	- Remote VPN access, 802.1X network Access
- RADIUS services available on almost any server operating system
- Operates on port 182
- Provides centralized Authentication, Authorization, and accounting management for users who connect and use a network service
- Uses a Server Secret Key to provide AAA
- Characteristics:
	- Primarily used for network access
	- Encrypts only the password in the access-request payload
	- Combines authentication and authorization
### TACACS
- Terminal Access Controller Access-Control System
	- Remote authentication protocol
	- Created to control access to dial-up lines to ARPANET
#### TACACS+
- The latest version of TACAS, not backwards compatible
- Cisco developed
- More authentication requests and response codes
- Released as an open standard in 1993
- Is a AAA (Accounting, Authorization and authentication) protocol to provide AAA services for access to routers, network access points, and other networking devices.
	- Uses sever secret key (a shared secret key). A mismatch could cause login problems. 
		- Is a text string that serves as a password between hosts
- A remote authentication protocol, which allows a remote access server to communicate with an authentication server to validate user access onto the network.
- Allows a client to accept a username and password and pass a query to a TACACS+ authentication server.
- Characteristics:
	- Encrypt the entire payload of the access-request packet
	- Primarily use for device administration
	- Separates authentication and authorization
### LDAP (Lightweight Directory Access Protocol)
- Protocol for reading and writing directories over an IP network
	- An organized set of records, like a phone directory
- X.500 specification was written by the International Telecommunication Union (ITU)
- DAP ran on the OSI protocol stack
	- LDAP is lightweight and uses TCP/IP (TCP/389, UDP/389)
- LDAP is the protocol used to query and update an X.500 directory
	- Used in Windows Active Directory, Apple OpenDirectory, OpenLDAP, etc
- Hierarchical structure - builds a tree
- Container objects
	- Country, organization, organizational units
- Leaf objects
	- Users, computers, printers, files
### Kerberos
- Network authentication protocol
	- Authenticate once, trusted by the system
- No need to re-authenticate to everything
	- Mutual authentication - the client and the sever
	- Protect against man-in-the-middle or replay attacks
- Standard since 1980s
	- Developed by MIT - RFC 4120
- Microsoft starting using Kerberos in Windows 2000
	- Based on Kerberos 5.0 open standard
	- Compatible with other operating system and devices
- Designed to provide strong mutual authentication for client/server applications using secret-key cryptography
- Designed to send data over insecure networks while using strong encryption to protect the information
	- RADIUS, TACACS+, PAP are all protocols that contain known vulnerabilities that would require additional encryption to secure them during the authentication process.
- Used to enable SSO
- NTP ensures the reliability of the Kerberos authentication process
### SSO with Kerberos
- Authenticate one time
	- Lots of backend ticketing, uses cryptographic tickets
- No constant username and password input! - Save time
- Only works with Kerberos
	- Not everything is Kerberos-friendly
- There are many other SSO methods
	- Smart-cards, SAML, etc
- Which method to use?
	- Many different ways to communicate to an authentication server
		- More than a simple login process
- Often determined by what is at hand
	- VPN concentrator can talk to a RADIUS server
	- We have a RADIUS server
- TACACS+ - Probably a Cisco device
- Kerberos or LDAP - Probably a Microsoft network
### IEE 802.1X
- Port-based Network Access Control (NAC)
- You don't get access to the network until you authenticate
- EAP integrates with 802.1X
	- Extensible Authentication Protocol
	- 802.1X prevents access to the network until the authentication succeeds
- Used in conjunction with an access database
	- RADIUS, LDAP, TACACS+
### EAP
- Extensible Authentication Protocol (EAP)
	- An authentication framework
- Many different ways to authenticate based on RFC standards
	- Manufactures can build their own EAP methods
- EAP integrates with 802.1X
	- Prevents access to the network until the authentication succeeds
## Risk Management
### Threat assessment
- Research the threats
	- and the threat actors
- Data is everywhere
	- Hacker group profiles, tool used by the attackers, and much more
- Make decisions based on this intelligence
	- Invest in the best prevention
- Used by researchers, security operations teams, and others
### Vulnerability assessment
- Usually minimally invasive
	- Unlike a penetration test
- Run a vulnerability scanner
	- Poke around and see what's open
- Identify systems
	- and security devices
- Test from the outside and inside
	- Don't dismiss insider threats
- Gather as much information as possible
	- We'll separate wheat from chaff later
### Vulnerability scan results
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
### Penetration testing
- Pentest - simulate an attack
- Similar to vulnerability scanning
	- Except we actually try to exploit the vulnerabilities
- Often a compliance mandate
	- Regular penetration testing by a 3rd party
- NIST
- Technical Guide to Information Security
- Testing and Assessment
	- https://professormesser.link/800115
### Posture Assessment
- You can't trust everyone's computer
	- BYOD (Bring Your Own Device)
	- Malware Infections / missing anti-malware 
	- Unauthorized applications
- Before connecting to the network, perform a health check
	- Is it a trusted device
	- Is it running anti-virus? Which one? Is it updated?
	- Are the corporate applications installed?
	- Is it a mobile device? Is the disk encrypted?
	- The type of device doesn't matter - Windows, Mac, Linux, iOS, Android
### Failing your assessment
- What happens when a posture assessment fails?
	- Too dangerous to allow access
- Quarantine network, notify administrators
	- Just enough network access to fix the issue
- Once resolved, try again - May required additional fixes
### Risk assessment
- Identify assets that could be affected by an attack
	- Define the risk associated with each asset
	- Hardware, customer data, intellectual property
- Identify threats - loss of data, disruption of services, etc
- Determine the risk - High, medium or low risk
- Process assessment - Make future security plans
### Vendors
- Every organization works with vendors
	- Payroll, customer relationship management, email marketing, travel, raw materials
- Important company data is often shared
	- May be required for cloud-based services
- Perform a risk assessment
	- Categorize risk by vendor and manage the risk
- Use contracts for clear understanding
	- Make sure everyone understands the expectations
	- Use the contract to enforce a secure environment
### SIEM
- Security Information and Event Management
	- Logging of security events and information
- Security Alerts
	- Real-time information
- Log aggregation and long-term storage
	- Usually includes advanced report features
- Data correlation
	- Link diverse data types
- Forensic analysis
	- Gather details after an event
### Getting the data
- Sensors and logs
	- Operating systems
	- Infrastructure devices
	- NetFlow sensors
- Sensitivity settings
	- Easy to be overwhelmed with data
	- Some information is unnecessary
	- Informational, Warning, Urgent
### Viewing the data
- Trends
	- Identify changes over time
	- Easily view constant attack metrics
- Alerts
	- Identify a security event
	- View raw data
	- Visualize the log information
- Correlation
	- Combine and compare
	- View data in different ways