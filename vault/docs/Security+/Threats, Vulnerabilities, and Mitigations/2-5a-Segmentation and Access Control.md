# 2.5a - Segmentation and Access Control
## Segmenting the network
- Physical, logical, or virtual segmentation
	- Devices, VLANs, virtual networks
- Performance
	- High-bandwidth applications
- Security
	- Users should not talk directly to database servers
	- The only applications in the core are SQL and SSH
- Compliance
	- Mandated segmentation (PCI compliance)
	- Makes change control much easier
## Access control lists (ACLs)
- Allow or disallow traffic
	- Groupings of categories
	- Source IP, Destination IP, port number, time of day, application, etc
- Restrict access to the network devices
	- Limit by IP address or other identifier
	- Prevent regular user / non-admin access
- Be careful when configuring these
	- Can accidentally lock yourself out
- List the permissions
	- Bob can read files
	- Fred can access the network
	- James can access 192.168.1.0/24 using TCP 80, 443, 8088
- Many operating systems use ACLs to provide access to files
	- A trustee and the access rights allowed
	- Application allow list / deny list
## Examples of allow and deny lists
- Decisions are made in the operating system
	- Often built-in to the operating system mangement
- Application hash
	- Only allows applications with this unique identifier
- Certificate
	- Allow digitally signed apps from certain publishers
- Path
	- Only run applications in these folders
- Network zone
	- The apps can only run from this network zone