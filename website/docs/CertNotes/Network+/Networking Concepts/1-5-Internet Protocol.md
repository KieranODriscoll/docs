# 1.5 - Internet Protocol
## A Series of Moving Vans
- Efficiently move large amounts of data
	- Use a shipping truck
- The network topology is the road
	- Ethernet, DSL, coax cable
- The truck is the Internet Protocol (IP)
	- We've designed the roads for this truck
- The boxes hold your data
	- Boxes of TCP and UDP
- Inside the boxes are more things
	- Application information
![Pasted_image_20240605165837](//assets/Pasted_image_20240605165837.webp)
## TCP and UDP
- Transported inside of IP
	- Encapsulated by the IP protocol
- Two ways to move data from place to place
	- different features for different applications
- OSI Layer 4
	- The transport layer
- Muiltiplexing
	- Use many different applications at the same time
	- TCP and UDP
### TCP - Transmission Control Protocol
- Connection-oriented
	- A formal connection setup and close
- "Reliable" delivery
	- Recovery from errors
	- Can manage out-of-order messages or retransmissions
- Flow control
	- The retriever can manage how much data is sent
![Pasted_image_20240605170214](//assets/Pasted_image_20240605170214.webp)
### UDP - User Datagram Protocol
- Connectionless
	- No formal open or close to the connection
- "Unreliable" delivery
	- No error recovery
	- No reordering of data or retransmissions
- No flow control
![Pasted_image_20240605170224](//assets/Pasted_image_20240605170224.webp)
- Sender determines the amount of data transmitted
### Lots of Ports
- IPv4 sockets
	- Server IP address, protocol, server application port number
	- Client IP address, protocol, client port number
- Non-ephemeral ports - permanent port numbers
	- Ports 0 through 1,023
	- Usually on a server or service
- Ephemeral ports - temporary port numbers
	- Ports 1024 through 65535
	- Determined in real-time by the client
### Port Numbers
- TCP and UDP ports can be any number between 0 and 65,535
- Most servers (services) use non-ephemeral port numbers
	- This isn't always the case - it's just a number
- Port numbers are for communication, not security
- Service port numbers need to be "well known"
- TCP port numbers aren't the same as UDP port numbers
### ICMP
- Internet Control Message Protocol
	- "Text messaging" for your network device
- Another protocol carried by IP - not used for data transfer
- Devices can request and reply to administrative requests
	- Hey are you there / yes I am
- Devices can send messages when things don't go well
	- That network you're trying to reach is not reachable from here
	- Your time-to-live expired
## Common Ports
### Telnet
- Telnet - Telecommunication Network
	- TCP/23
	- Login to devices remotely
	- Console access
	- Clear text communication
- Provides username & password authentication
### SSH - Secure Shell
- Encrypted communication link - tcp/22
- Looks and acts the same as Telnet
### DNS - Domain Name System
- Convert names to IP address - udp/53
- Larger transfers may use tcp/53
- These are very critical resources
	- Usually multiple DNS servers are in production
### SMTP - Simple Mail Transfer Protocol
- Server to server email transfer - tcp/25
- Also used to send mail from a device to a mail server
- Commonly configured on mobile devices and email clients
- Other protocols are used for clients to receive email
	- IMAP, POP3
- TLS for encryption
	- 587/TCP
- Sending email messages between mail servers
- Sending email messages from a client device
### POP/IMAP
- Receive emails from an email server
	- Authenticate and transfer
- POP3 - Post Office Protocol Version 3 - tcp/110
	- Basic mail transfer functionality
	- Email retrieval
- IMAP4 - Internet Message Access Protocol v4 - tcp/143
	- Manage email inbox from multiple clients
	- Offers improved functionality in comparison to POP3
	- Serves the same function as POP3
- POP3 SSL/TLS - 995/TCP
- IMAP SSL/TLS - 993/TCP
### SFTP - Secure FTP
- Uses the SSH File Transfer Protocol - TCP/22
- Provides file system functionality
	- Resuming interrupted transfers, directory listings, remote file removal
### File Transfer application protocols
- FTP -File Transfer Protocols
	- TCP/20 (active mode data), TCP/21 (control)
	- Transfers files between systems
	- Authenticates with a username and password
	- Full-featured functionality (list, add, delete, etc)
- TFTP - Trivial File Transfer Protocol
	- UDP/69
	- Very simple file transfer application
		- Read files and write files
	- No authentication - not used on production systems
	- Often used for internal network servers for delivering software upgrades to network devices
### DHCP - Dynamic Host Configuration Protocol
- Automated configuration of IP address, subnet mask and other options
	- UDP/67, UDP/68 - Requires a DHCP server
- Dynamic / pooled
	- IP addresses are assigned in real-time from a pool
	- Each system is given a lease
	- Must renew at set intervals
- Reserved
	- Addresses are assigned by MAC address
	- Quickly manage addresses from on location
### HTTP and HTTPS
- SSL - 80/TCP and 443/TCP
- TLS - 995/TCP and 465/TCP
- Hypertext Transfer Protocol
	- Communication in the browser
	- used by other applications as well
- Clear text for HTTP or encrypted for HTTPS
- Supported by nearly all web servers and clients
### SNMP - Simple Network Management Protocol
- Gather statistics from network devices - UDP/161 and UDP/162
- Network management systems protocol for monitoring network-attached devices
- Requires the agents to be installed on the devices
- Uses Network Management System (NMS) to question the agents
- Uses Management information Base (MIB) to question agents
	- A translation file that is used to describe the structure of the management data of a device subsystem using hierarchical namespace containing object identifiers (OID)
- V1 - Original
	- Structured tables, clear text
- V2 - a good step
	- Data type enhancements, bulk transfers
	- Still clear text
- V3 - Standard
	- Message integrity, authentication, encryption
	- AuthPriv option ensures that the communications are sent with authentication and privacy. This uses MD5 and SHA for authentication and DES and AES for privacy and encryption
- A trap is an asynchronous notification from the agent to the manager. A trap is sent by the agent to notify the management of a significant event that is occurring in real-time, such as an alarming condition
- A verbose trap may contain all the information about a given alert or event as its payload.
- A granular trap contains a unique object identifier (OID) number and a value for that OID. A verbose trap contains more information and data than a granular trap
- A verbose trap requires more bandwidth to send
- Unique Objective Identifier (OID) identifies a variable that can be read or set using the SNMP protocol
- Management Information Base (MIB) is a translation file that is used to describe the structure of the management data of a device subsystem using a hierarchical namespace containing object identifiers (OID)
### Syslog
- Standard for message logging
	- Diverse systems, consolidation of log
	- UDP/514
- Is used as a log repository that collects logs from various devices and servers on a network
- Allows you to sort and search logs
- Allows you to use various severity levels for events that are stored in logs
- Usually a central log collector
	- Integrated into the SIEM
- You're going to need a lot of disk space
	- Data storage from many devices over an extended timeframe
### RDP - Remote Desktop Protocol
- Share a desktop from a remote location over TCP/3389
- Remote Desktop Services on many Windows versions
- Can connect to an entire desktop or just an application
- Clients for Windows, MacOS, Linux, IPhone and others
### NTP - Network Time Protocol
- Switches, routers, firewalls, servers, workstation
	- Every device has its own clock - UDP/123
- Synchronizing the clocks becomes critical
	- Log files, authentication information, outage details
- Automatic updates
- Flexible- control how clocks are updated
- Very accurate - accuracy is better than 1 millisecond
### SIP - Session Initiation Protocol
- VOIP signaling
	- TCP/5060 and TCP/5061
- Setup and manage VoIP sessions
	- Call, ring hang up
- Extend Voice Communication
	- Video Conferencing, instant messaging, file transfer, etc
- Used for:
	- Online Games, Instant messaging, Streaming media, Videoconferencing, Audio and Video calls
- Initiates, manages and terminates the real-time sessions
### Real-time Transport Protocol
- Multicast protocol
- Designed for audio and video delivery over Internet
- Is now a standard for VoIP
- Uses 5004/UDP and 5005/TCP
- Payload protocol that sends and receives audio over the internet
### SMB - Server Message Block
- Protocol used by Microsoft Windows
- File sharing, printer sharing
- Also called CIFS (Common Internet File System)
- Direct over TCP/445 (NetBIOS-less)
- 137/UDP, 138/UDP
- 137/TCP, 139/TCP using NetBIOS
- Direct SMB communication over TCP
### LDAP/LDAPS
- Lightweight Directory Access Protocol - TCP/389
- Store and retrieve information in a network directory
- LDAPS (Secure) - TCP/636
	- A non-standard implementation of LDAP over SSL
- Directory Access Protocol
### Databases
- Microsoft SQL Server - TCP/1433
- Oracle SQL *Net
	- Also called Oracle Net or Net8 - TCP/1521
- MySQL free and open-source database
	- Ultimately acquired by Oracle - TCP/3306
![Pasted_image_20240606131846](//assets/Pasted_image_20240606131846.webp)

## Other Useful Protocols
### GRE
- Generic Routing Encapsulation
	- The tunnel between two endpoints
- Encapsulate traffic inside of IP
	- Two endpoints appear to be directly connected to each other
	- No built-in encryption
### VPNs
- Virtual Private Networks
- Encrypted data traversing a public network
- Concentrator
	- Encryption/Decryption access device
	- Often integrated into a firewall
- Many deployment options
	- Specialized cryptographic hardware
	- Software-based options available
- Used with client software
	- Sometimes built into the OS
### AH (Authentication Header)
- Data integrity
- Origin authentication
- Replay attack protection
- Keyed-hash mechanism
- No confidentiality/encryption
- ![[Pasted image 20240606132103.png]]
### ESP (Encapsulating Security Payload)
- Data confidentiality (encryption)
- Limited traffic flow confidentiality
- Data integrity
- Anti-replay protection
- ![[Pasted image 20240606132152.png]]
### IPSec (Internet Protocol Security)
- Security for OSI Layer 3
	- Authentication and encryption for every packet
- Confidentiality and integrity/anti-replay
	- Encryption and packet signing
- Very standardized
	- Common to use multi-vendor implementations
- Two core IPSec protocols
	- Authentication Header (AH)
		- Provides authentication and integrity
	- Encapsulation Security Payload (ESP)
		- Provides authentication, integrity and confidentiality
### IPSec Transport mode and Tunnel Mode
- Combine the data integrity of AH with the confidentiality of ESP
- Tunnel mode
	- Encrypts the entire packet
- Transport mode
	- Provides only encryption for the payload
- ![[Pasted image 20240606132631.png]]
