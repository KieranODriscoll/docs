# 3.2a - Secure Infrastructures
## Device placement
- Every network is different
	- There is often similarities
- Firewalls
	- Separate trusted from untrusted
	- Provide additional security checks
- Other services may require their own security technologies
	- Honeypots, jump server, load balancers, sensors
## Security zones
- Zone-based security technologies
	- More flexible (and secure) than IP address ranges
- Each are of the network is associated with a zone
	- Trusted, untrusted
	- Internal, external
	- Inside, Internet, Servers, Databases, Screened
- This simplifies security policies
	- Trusted to untrusted
	- Untrusted to screened
	- Untrusted to Trusted
## Attack surface
- How many ways into your home?
- Everything can be a vulnerability
	- Application Code
	- Open Ports
	- Etc
- Authentication process
	- Human error
- Minimize the surface
	- Audit the code
	- Block ports on the firewall
	- Monitor network traffic in real-time
## Connectivity
- Everything contributes to security
	- Including the network connection
- Secure network cabling
	- Protect the physical drops
- Application-level encryption
	- The hard work has already been done
- Network-level encryption
	- IPSec tunnels, VPN connections
![](Pasted%20image%2020240913142241.png)