# 4.3 - Hardening
## Network Hardening
### DHCP snooping
- IP tracking on a layer 2 device (switch)
	- The switch is a DHCP firewall
	- Trusted: Routers, switches, DHCP servers
	- Untrusted: Other computers, unofficial DHCP servers
- Switch watches for DHCP conversations
	- Adds a list of untrusted devices to a table
- Filters invalid IP and DHCP information
	- Static IP addresses
	- Devices acting as DHCP servers
- Other invalid traffic patterns
- Improves the security of a DHCP infrastructure. When DHCP servers are allocating IP addresses to LAN clients, DHCP snooping can be configured on LAN switches to prevent malicious or malformed DHCP traffic or rogue DHCP servers
### Dynamic ARP inspection (DAI)
- ARP is powerful
	- and has no built-in security
- Prevent those nasty on-path attacks
	- Stops ARP poisoning at the switch level
- Relies on DHCP snooping for intel
	- Knowing every device's IP can be valuable information
- Intercept all ARP requests and responses
	- Invalid IP-to-MAC address bindings are dropped
	- Only valid requests make it through
- Validates Address Resolution Protocol (ARP) packets in the network.
- Allows a network administrator to intercept, log and discard ARP packets with invalid MAC address to IP address bindings
### Control plan policing
- Control plane manages the device
	- Data plane performs the operational processes
- Protect against DoS or reconnaissance
	- Defines a QoS filter to protect the control plane
	- Control packets should have the priority
- Manage traffic
	- Prioritize management traffic
	- Block unnecessary control plane traffic types
	- Rate limit the control plane traffic flows
### Private VLANs
- Port isolation
	- Restrict access between interfaces
	- Even when they're in the same VLAN
- You might already be using private VLANs
	- Your home internet can't directly connect to another home
	- Hotel room access is limited to Internet connectivity
### Disabling unused interfaces
- Enabled physical ports
	- Conference rooms
	- Break rooms
- Administratively disable unused ports
	- More to maintain, but more secure
- Network Access Control (NAC)
	- 802.1X controls
	- You can't communicate unless you are authenticated
	- Means of ensuring endpoint security by ensuring that all devices connecting to the network conform to a health policy
	- Set of protocols to define and implement a policy that describes how to secure access to network nodes whenever a device initially attempts to access the network
	- Utilize an automatic remediation process by fixing non-compliant hosts before allowing network access
	- Can control access to a network with policies, including pre-admission endpoint security policy checks and post-admission controls over where users and devices can go on a network and what they can do
	- Can also determine unknown machines and provide them with direct internet access only by placing them onto a guest network or VLAN
	- An approach to computer security that attempts to unify endpoint security technology, the user or system authentication and network security enforcement
	- Restricts the data that each particular user can access and implements anti-threat applications such as firewalls, anti-virus software and spyware detection programs.
	- Also regulates and restricts the things individual subscribers or users can do once they are connected
	- If a user is unknown, the NAC can quarantine the device from the network upon connection
### Disable unnecessary ports and services
- Every open port is a possible entry point
	- Close everything except required ports
- Control access with a firewall
	- NGFW would be ideal
- Unused or unknown services
	- Installed with the OS or from other applications
- Applications with broad port ranges
	- Open port 0 through 65,535
- Use Nmap or similar port scanner to verify
	- Ongoing monitoring is important
### Changing default credentials
- Most devices have default usernames and passwords
	- Change yours!
- The right credentials provide full control
	- Administrator access
- Very easy to find the defaults for your AP or router
### Password complexity and length
- Make your password strong
	- Resist guessing or brute-force attack
- Increase password entropy
	- No single words, no obvious passwords
	- What's the name of your dog
	- Mix upper and lower case and use special characters
	- Don't replace a o with a 0, t with a 7
- Stronger passwords are at least 8 characters
	- Consider a phrase or set of words
### Change default VLAN
- All access ports (non-trunk ports) are assigned to a VLAN
	- Without any additional security (802.1x), anyone connecting will be part of the default VLAN
- The default VLAN might also be used by default for control plan access/management
	- Don't put users on the management VLAN
	- Change the management VLAN to something exclusive
- Assign unused interfaces to a specific non-routable, non-forwarding VLAN
	- a "dead-end" or "impasse" VLAN
### Upgrading firmware
- Many network devices do not use a traditional operating system
	- All updates are made to firmware
- The potential exists for security vulnerabilities
	- Upgrade the firmware to a non-vulnerable version
- Plan for the unexpected
	- Always have a rollback plan
	- Save those firmware binaries
### Patch Management
- Incredibly important
	- System stability
	- Security fixes
- Service packs
	- All at once
- Monthly updates
	- Incremental (and important)
- Emergency out-of-band updates
	- Zero-day and important security discoveries
### Role-based access
- Not everyone connecting to a switch or router needs the same level of access
- Many devices allow the configuration of the specific roles
	- Rights and permissions are based on the role
	- Administrators can configure and reboot the device
	- Help desk can view statistics
	- API access can't interactively login/SSH
### Access control lsits (ACLs)
- Allow or disallow traffic based on tuples
	- Groupings of categories
	- Source IP, Destination IP, port number, time of day, application, etc
- Restrict access to network devices
	- Limit by the IP address or other identifier
	- Prevent regular user / non-admin access
- Be careful when configuring these
	- You can accidentally lock yourself out
### Firewalls
#### Stateful Firewall
- Enhances security through packet filtering, and these types of firewalls also keep track of outbound requests and open the port for returning traffic to enter the network
- Monitors the active sessions and connections on a network
- Determines which network packets should be allowed through the firewall by utilizing the information it gathered regarding active connections as well as the existing ACL rules
- Does not operate at layer 6 or layer 7, so they cannot inspect the contents of the packet
#### Application-aware Firewall
- Can make decisions about what applications are allowed or blocked by a firewall, as opposed to simply using IP addresses and port numbers, by inspecting the data contained within the packets
#### Stateless Packet Inspection Firewall
- Allows or denies packets into the network based on the source and destination IP address or the traffic type (TCP, UDP, ICMP, etc)
#### Firewall Rules
- Manage access from the firewall
	- Additional security options - Username, VPN, MFA
- Most firewall rules include an implicit deny
	- If there's no explicit rule, then traffic is blocked
	- These implicit deny rules aren't usually logged
- Some firewall administrators will add explicit deny rules
	- Anything denied by a rule is logged by default
	- Can be useful for identifying reconnaissance or access attempts
## Wireless Security
### MAC Filtering
- Media Access Control
- Limit access through the physical hardware address
	- Keeps the neighbors out
	- Additional administration with visitors
- Easy to find working MAC addresses through wireless LAN analysis
	- MAC addresses can be spoofed
	- Free open-source software
- Security through obscurity
	- If you know the method, you can easily defeat it
### Antenna placement
- Focus coverage to the necessary work areas
	- Limit access from outside the building
- Adjust power levels
	- Control coverage based on signal strength
- May require some additional site surveys
	- Walk around and optimize the coverage
### Wireless isolation
- Wireless client isolation
	- Wireless devices on an access point can't communicate with each other
	- Useful in a hotel or public area
	- May not be useful at work with peer-to-peer applications
- Guest network isolation
	- The guest network does not have access to the internal private network
	- This is almost always the right configuration
### Wireless security modes
- Configure the authentication on your access point / wireless router
- Open system - no auth password required
- WPA2/3-Personal / WPA-PSK
	- WPA2 or WPA3 with a pre-shared key
	- Everyone uses the same 256-bit key
- WAP2/3-Enterprize / WPA2/3-802.1X
	- Authenticate users individually with an authentication server (RADIUS, LDAP)
	- Requires authentication server to be u sed
### EAP
- Extensible Authentication Protocol
	- An authentication framework
- Many different ways to authenticate based on RFC standards
	- WPA2 and WPA3 use five EAP types as authentication methods
- Some version of EAP is used when authenticating to the network
	- Common to integrate on wireless networks using 802.1X
### Geofencing
- Some MDMs allow for geofencing
	- Restrict or allow a features when the device is in a particular area
- Cameras
	- The camera might only work when outside the office
- Authentication
	- Only allow logins when the device is located in a particular area
### Captive Portal
- Authentication to a netowrk
	- Common on wireless networks
- Access table recognizes a lack of authentication
	- Redirects your web access to a captive portal page
- Username / password
	- and additional authentication factors
- Once proper authentication is provided, the web session continues
	- Until the captive portal removes your access
- Uses DNS redirect, ICMP redirect, HTTP redirect
- Usually relies on 802.1x and 802.1x uses RADIUS for authentication
### IoT Security
- Internet of things devices
- Security is probably not the primary focus
- IoT devices should be segmented from the private network
	- Keep your personal devices and storage systems away from IoT devices
	- If an IoT device is breached, your personal data is not accessible
- Use a separate VLAN
	- Many homes access points provide a "guest" network
	- This is different than the DMZ or screened-subnet

## Data Destruction
### Wiping
- Also known as cleaning occurs by using a software tool to overwrite the data on a hard drive to destroy all electronic data on a hard disk or other media
- 1x, 7x, 35x overwriting with a higher number of times being more secure
- Allows the hard drive to remain functional and allows for hardware reuse
### Degaussing
- Involves demagnetizing a hard drive to erase its stored data.
- You cannot reuse a hard drive once it has been degaussed
### Purging
- Removing sensitive data from a hard drive using the device's internal electronics or an outside source such as a degausser, or by using a cryptographic erase function
### Shredding
- Physical destruction of the hard drive.
- Secure method of destruction but doesn't allow for device reuse
## Unified Threat Management (UTM)
- Appliance that enforces a variety of security-related measures, combining the work of a firewall, malware scanner, and intrusion detection/prevention.
- Centralizes the threat management service, providing simpler configuration and reporting than isolated applications spread across several servers or devices
