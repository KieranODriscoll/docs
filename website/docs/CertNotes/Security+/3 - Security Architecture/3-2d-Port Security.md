# 3.2d - Port Security
## Port security
- We've created many authentication method through the years
	- A network administrator has many choices
- Use a username and password
	- Other factors can be included
- Commonly used on wireless networks
	- Also works on wired networks
## EAP
- Extensible Authentication Protocol (EAP)
	- An authentication framework
- Many different ways to authenticate based on RFC standards
	- Manufacturers can build their own EAP methods
- EAP integrates with 802.1X
	- Prevents access to the network until the authentication succeeds
## IEEE 802.1x
- IEEE 802.1X
	- Port-based Network Access Control (NAC)
	- You don't get access to the network until you authenticate
- EAP (Extensible Authentication Protocol)
	- 802.1X prevents access to the network until the authentication succeeds
- Used in conjunction with an authentication database
	- RADIUS, LDAP, TACACS+, Kerberos, etc
## IEEE 802.1X and EAP
- Supplicant - the client
- Authenticator - The device that provides access
- Authentication server - Validates the client credentials
