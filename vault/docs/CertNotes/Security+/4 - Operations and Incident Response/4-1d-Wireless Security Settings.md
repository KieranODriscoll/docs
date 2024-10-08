# 4.1d - Wireless Security Settings
## Securing a wireless network
- An organization's wireless network can contain confidential information
	- Not everyone is allowed access
- Authenticate the users before granting access
	- Who gets access to the wireless network?
	- Username, password, multi-factor authentication
- Ensure that all communication is confidential
	- Encrypt the wireless data
- Verify the integrity of all communication
	- The received data should be identical to the original sent data
	- A message integrity check (MIC)
## The WPA2 PSK problem
- WPA2 has a PSK brute-force problem
	- Listen to the four-way handshake
	- Some methods can derive the PSK hash without the handshake
	- Capture the hash
- With the hash, attackers can brute force the pre-shared key (PSK)
- This has become easier as technology improves
	- The weak PSK is easier to brute force
	- GPU processing speeds
	- Cloud-based password cracking
- Once you have the PSK, you have everyone's wireless key
	- There's no forward secrecy
## WPA3 and GCMP
- Wi-Fi Protected Access 3 (WPA3)
	- Introduced in 2018
- GCMP block cipher mode
	- Galois/Counter Mode Protocol
	- A stronger encryption than WPA2
- GCMP security services
	- Data confidentiality with AES
	- Message Integrity Check (MIC) with
	- Galois Message Authentication Code (GMAC)
- AES is currently the most secure and widely adopted encryption protocol for wireless networks. Recommended choice for ensuring robust security in wireless communication
	- AES is a symmetric encryption algorithm
## SAE
- WPA3 changes the PSK authentication process
	- Include mutual authentication
	- Creates a shared session key without sending that key across the network
	- No more four-way handshakes, no hashes, no brute force attacks
- Simultaneous Authentication of Equals (SAE)
	- A Diffie-Hellman derived key exchange with an authentication component
		- Protocol that generates temporary keys for each session, providing forward secrecy to protect past and future communication
	- ECDHE
		- Key exchange protocol that leverages ECC for enhanced security and efficiency
	- Everyone uses a different session key, even with the same PSK
	- An IEEE standard - the dragonfly handshake
## Wireless authentication methods
- Gain access to a wireless network
	- Mobile users, temporary users
- Credentials
	- Shared password / pre-shared key (PSK)
	- Centralized authentication (802.1X)
- Configuration
	- Part of the wireless network connection
	- Prompted during the connection process
## Wireless security modes
- Configure the authentication on your wireless access point / wireless routerr
- Open System
	- No authentication password is required
- WPA3 - Personal / WPA3-PSK
	- WPA and WPA3 with a pre-shared key
	- Everyone uses the same 256-bit key
- WPA3-Enterprise / WPA3-802.1X
	- Authentication users individually with an authentication server (ie. RADIUS)
## AAA Framework
- Identification
	- This is who you claim to be - usually a username
- Authentication
	- Prove you are who you say you are
	- Password or other authentication factors
- Authorization
	- Based on your identification and authentication, what access do you have?
- Accounting
	- Resources used: Login time, data sent and received, logout time
## RADIUS (Remote Authentication Dial-in User Service)
- One of the more common AAA protocols
	- Supported on a wide variety of platforms and devices
	- Not just for dial-in
- Centralized authentication for users
	- Routers, switches, firewalls
	- Server authentication
	- Remote VPN access
	- 802.1X network access
- RADIUS services available on almost any server operating system
## IEEE 802.1X
- Port-based Network Access Control (NAC)
	- You don't get access to the network until you authentication
- Used in conjunction with an access database
	- RADIUS, LDAP, TACACS+
- TACACS+
	- Characteristics
		- Encrypts the entire payload of the access-request packet
		- Primarily used for device administration
		- Separates authentication and authorization
- Radius
	- Characteristics
		- Encrypts only the password in the access-request packet
		- Primarily used for network access
		- Combines authentication and authorization
## EAP
- Extensible Authentication Protocol (EAP)
	- An authentication framework
- Many different ways to authenticate based on RFC standards
	- Manufacturers can build their own EAP methods
- EAP integrates with 802.1X
	- Prevents access to the network until the authentication succeeds
## IEEE 802.1X and EAP
- Supplicant - the client
- Authenticator - The device that provides access
- Authentication server - Validates the client credentials