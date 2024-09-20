# 4.4 - Remote Access
## VPNs
- Virtual Private Network
	- Encrypted data traversing a public network
- Concentrator
	- Encryption/Decryption access device
	- Often integrated into a firewall
- Many deployment options
	- Specialized cryptographic hardware
	- Software-based options available
- Used with client software
	- Sometimes built into the OS
### Site-to-site VPNs
- Encrypted traffic between sites
	- Through the public internet
- Use existing internet connection
	- No additional circuits or costs
- ![[Pasted image 20240613133834.png]]
### Host-to-Site VPNs
- Also called "remote access VPN"
- Requires software on the user device
	- May be built-in to existing operating system
- ![[Pasted image 20240613133950.png]]
### Clientless VPNs
- Hypertext Markup Language Version 5
	- The language commonly used in web browsers
- Includes comprehensive API support
- Creates a VPN tunnel without a separate VPN application
- Use an HTML5 compliant browser
	- Communicate directly to the VPN concentrator
## Remote Desktop Connection
- Share a desktop from a remote location
- RDP (Microsoft Remote Desktop Protocol)
	- Clients for Mac OS, Linux, and others as well
- VNC (Virtual Network Computing)
	- Remote Frame Buffer (RFB) protocol
	- Clients for many operating systems 
	- Many are open source
- Commonly used for technical support
	- And for scammers
### Remote Desktop Gateway
- Combine a VPN with Microsoft Remote Desktop
	- Securely access RDP servers from the outside
- Clients connects to the Remote Desktop Gateway
	- Secure SSL tunnel
	- Many authentication options
- Remote Desktop Gateway connects internally to RDP servers over TCP/3389
	- No special configuration required
	- Gateway is the proxy between the SSL tunnel and the Remote Desktop protocol
## SSH (Secure Shell)
- Encrypted console communication - TCP/22
- Looks and acts the same as Telnet - TCP/23
## Cloud-hosted virtual desktops
- A virtual desktop infrastructure (VDI) in the cloud
	- Users connect to a pre-built desktop
- Access from almost an OS
	- Windows, MAC, Linux, iOS, Chromebook, Web browser, Android
- Virtual NIC
	- All communication in the desktop are local to the virtual desktop
	- No sensitive information sent from the local device
## Authentication and Authorization
- 2008 until May 2011 - Subway Sandwiches
	- 200 Locations were breached
	- Point of sale systems were equipped with remote desktop software
	- 80,000 credit cards, millions of dollars of unauthorized purchases
- Significant security issues
	- Default credentials and brute force attacks
	- Remote access requires more security, not less
- Once connected, authorization is key
	- Access rights should be limited
## Out-of-band management
- The network isn't available
	- Or the device isn't accessible from the network
- Most devices have a separate management interface
	- Usually a serial connection / USB
- Connect a modem
	- Dial-in to manage the device
- Console Router / Comm server
	- Out-of-band access from multiple devices
	- Connect to the counter router, then choose where you want to go