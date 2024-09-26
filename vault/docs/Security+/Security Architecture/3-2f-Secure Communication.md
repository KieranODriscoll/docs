# 3.2f - Secure Communication
## VPNs
- Virtual Private Networks
	- Encrypted (private) data traversing a public network
- Concentrator
	- Encryption/decryption access device
	- Often integrated into a firewall
- Many deployment options
	- Specialized cryptographic hardware
	- Software-based options available
- Used with client software - Sometimes built into the OS
## Encrypted tunnel
- Keep data private across the public Internet
	- Encryption is the key
- Encrypt your data - Add new headers and trailers
- Decrypt on the other side - Original data is delivered
## SSL/TLS VPN (Secure Socket Layer VPN)
- Uses common SSL/TLS protocol (TCP/443)
	- (Almost) No firewall issues
- No big VPN clients
	- Usually remote access communication
- Authenticate users
	- No requirement for digital certificates or shared passwords (like IPSec)
- Can be run from a browser or from a (usually light) VPN client
	- Across many operating systems
- On-demand access from a remote device
	- Software connects to a VPN concentrator
- Some software can be configured as always-on
- ![[Pasted image 20240913190606.png]]
## Site-to-site IPsec VPN
- Always-on
	- Or almost always
- Firewalls often act as VPN concentrators
	- Probably already have firewalls in place
- ![[Pasted image 20240913190612.png]]
## SD-Wan
- Software Defined Networking in a Wide Area Network
	- A WAN built for the cloud
- The data center used to be in one place
	- The cloud has changed everything
- Cloud-based applications communicate directly to the cloud
	- No need to hop through a central point
## Secure Access Service Edge (SASE)
- Update secure access for cloud services
	- Securely connect from different locations
- Secure Access Service Edge (SASE)
	- A "next generation" VPN
- Security technologies are in the cloud
	- Located close to existing cloud services
- SASE clients on all devices
	- Streamlined and automatic
- ![[Pasted image 20240913190624.png]]
- Combines network security and WAN capabilities in a single cloud-based service, making it an ideal solution for ensuring secure and reliable access to data and applications irrespective of user/device location
- Form of cloud architecture that combines a number of services as as single service
## Selection of effective controls
- Many different security options
	- Selecting the right choice can be challenging
- VPN
	- SSL/TLS VPN for user access
	- IPSec tunnels for site-to-site access
- SD-Wan
	- Manage the network connectivity to the cloud
	- Does not adequately address security concerns
- SASE
	- A complete network and Security solution
	- Requires planning and implementation