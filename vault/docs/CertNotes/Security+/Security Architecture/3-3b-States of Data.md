# 3.3b - States of Data
## Data at rest
- The data is on a storage device
	- Hard drive, SSD, flash drive, etc
- Encrypt the data
	- Whole disk encryption
	- Database encryption
	- File- or folder-level encryption
- Apply permissions
	- Access control lists
	- Only authorized users can access the data
## Data in transit
- Data transmitted over the network
	- Also called data in-motion
- Not much protection as it travels
	- Many different switches, routers, devices
- Network-based protection
	- Firewall, IPS
- Provide transport encrypytion
	- TLS (Transport Layer Security)
	- IPSec (Internet Protocol Security)
		- Suite of protocols and technologies providing encryption, authentication, and data integrity for network traffic
## Data in use
- Data is actively processing in memory
	- System RAM, CPU registers and cache
- The data is almost always decrypted
	- Otherwise, you couldn't do anything with it
- The attackers can pick the decrypted information out of RAM
	- A very attractive option
## Data sovereignty
- Data sovereignty
	- Data that resides in a country is subjected to the laws of that country
	- Legal monitoring, court orders, etc
- Laws may prohibit where data is stored
	- GDPR (General Data Protection Regulation)
	- Data collected on EU citizens must be stored in the EU
	- A complex mesh of technology and legalities
- Where is your data stored?
	- Your compliance laws may prohibit moving data out of the country
## Geolocation
- Location details
	- Tracks within a localized area
- Many ways to determine location
	- 802.11, mobile providers, GPS
- Can be used to manage data access
	- Prevent access from other countries
- Limit administrative tasks unless secure area is used
	- Permit enhanced access when inside the building