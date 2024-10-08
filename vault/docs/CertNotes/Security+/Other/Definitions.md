# Defintions
## Operational Efficiency
- Effectiveness and productivity of operations but doesn't directly address the financial impact of a tool over its lifecycle
## Capital Expenditure (CAPEX)
- pertains to the initial costs to purchase the asset or tool, not the ongoing or total costs throughout its lifecycle
## Return on Investment
- Evaluates the profitability or benefit of a particular investment, doesn't focus on the entire financial impact over a tool's lifecycle
## Elliptic Curve Cryptography (ECC)
- Form of public key cryptography primarily used for digital signatures and key exchange
## Probability
- Refers to the expected frequency of occurrence of a specific risk within a given time frame
- This differs from ARO which is the annualized rate of occurrence and is a quantitative risk analysis metric that represents the expected number of times a specific risk occurs in a year
## Metadata
- Contains:
	- The name of the user who creates the file
	- File size
	- Date and time of last modification
- Does not contain the file extension
## Tunnel mode in IPSec
- Used for communications between VPN gateways across an insecure network
- Encrypts the whole IP packet, it doesn't
## Encapsulation Security Payload (ESP)
- part of the IPSec that provides confidentiality and/or authentication and integrity
## SD-WAN
- Optimizes network performance and centralizes network management. While it enhances WAN connections, it doesn't inherently combine network security and WAN capabilities
## Resource reuse
- Type of vulnerability that involves accessing or modifying data or communications from other virtual machines by exploiting the shared CPU between them
- Can allow an attacker to execute malicious code or commands on other virtual machines
## Race condition
- Situation where the outcome of a process depends on the timing or order of execution of other processes.
- Can cause errors, inconsistencies, or security breaches, depending on the nature and importance of the resource
## Time-of-check (TOC)
- Type of race condition that occurs when a process checks the state or value of a resource before using it, but another process changes it in between
- Can lead to incorrect or unauthorized actions based on outdated information
## CPU Starvation
- Type of performance issue that occurs when a process or thread does not receive enough CPU time to perform its tasks
- Affect the responsiveness and functionality of the process or thread
## Kerberos
- Authentication protocol that uses tickets to prevent eavesdropping and replay attacks
- Relies on a trusted third-party, the Key Distribution Center (KDC), to facilitate mutual authentication between clients and services
- KDC
	- Centralized server that is used to distribute cryptographic keys and authenticate users and services within a computer network
- TGT
	- Ticket Granting Tickets
		- Secure token is granted to users during their initial login to enable them access to multiple network services without the need to re-enter their login credentials
## Capability
- Pertains to a threat actor's proficiency in devising new exploit techniques and tools
- Can range from commonly found attack tools to creating zero-day exploits
- Those with the highest capabilities can even deploy non-cyber tools
## Sophistication
- Relates to the level of intricacy and advancement of a threat actor's method and tools, but not directly to their skill in crafting novel exploits
## Applications Monitoring
- Zeroes in on specific software solutions, evaluating their performance, security and ensuring that they operate without vulnerabilities or external compromises
## Infrastructure Monitoring
- Observing the overall health and security of foundational IT structures, like servers and networks, which provide the base for both systems and applications
## System monitoring
- Primarily emphasizes the security and functionality of the hardware and its core services
## New Technology LAN Manager (NTLM)
- least secure authentication service
- Creates an MD4 hash of a suer's password
- MD4 can be cracked and should be used
## RAID
### Level 0
- Requires a minimum of 2 drives to implement
- Is also known as disk striping
- Decreases reliability (failure of any disk in the array results in the loss of all data in the array)
- Is suitable for systems where performance has higher priority than fault tolerance
### Level 1
- Requires at least 2 drives to implement
- Offers improved reliability by creating identical data sets on each drive (failure of 1 drive does not destroy the array as each drive contains identical copy of the data)
- Also referred to as disk mirroring
### Level 5
- Requires at least 3 drives to implement
- Offers increased performance and fault tolerance (single drive failure does not destroy the array and lost data can be re-created by the remaining drives)
- Is also known as disk striping with parity
### Level 6
- Requires at least 4 drives to implement
- Offers increased performance and fault tolerance (failure of up to 2 drives does not destroy the array and lost data can be re-created by remaining drives)
- Is also known as disk striping with double parity
### Level 10 (Raid 1 + 0)
- Requires a minimum of 4 drives to implement
- Referred to as stripe mirrors, combination of RAID 1 (data mirroring) and RAID 0 (disk striping)
- Offers increase performance and fault tolerance (failure of one drive in each mirrored pair of disk drives does not destroy the array)
## TTP
- Tactics, Techniques and Procedures
## SPOF
- Single Point of Failure
## PKCS
- Public Key Cryptography Standards
## PBKDF2
- Key stretching algorithm
- Enables secure conversion of user passwords into cryptographic keys
## OVAL
- Language primarily used for automating the assessment of security vulnerabilities and configuration issues on computer systems
## CASB
- Cloud Access Security Broker
- Cloud-based security policy enforcement point between cloud service consumers and providers