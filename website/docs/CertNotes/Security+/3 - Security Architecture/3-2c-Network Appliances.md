# 3.2c - Network Appliances
## Jump server
- Access secure network zones
	- Provides an access mechanism to a protected network
- Highly-secured device
	- Hardened and monitored
- SSH / Tunnel / VPN to the jump server
	- RDP, SSH, or jump from there
- A significant security concern
	- Compromise of the jump server is a significant breach
## Proxies
- Sits between the users and the external network
- Receives the user requests and sends the request on their behalf (the proxy)
- Useful for caching information, access control, URL filtering, content scanning
- Applications may need to know how to use the proxy (explicit)
- Some proxies are invisible (transparent)
## Forward Proxy
- An "internal" proxy
- Commonly used to protect and control user access to the interner
![Pasted_image_20240913182644](//assets/Pasted_image_20240913182644.webp)
## Reverse Proxy
- Inbound traffic from the Internet to your internal service
![Pasted_image_20240913182722](//assets/Pasted_image_20240913182722.webp)
## Open Proxy
- A third-party, uncontrolled proxy
- Can be a significant security concern
- Often used to circumvent existing security controls
![Pasted_image_20240913182804](//assets/Pasted_image_20240913182804.webp)
## Application proxies
- One of the simplex "proxies" is NAT
	- A network-level proxy
- Most proxies in use are application proxies
	- The proxy understands the way the application works
- A proxy may only know one application
	- HTTP
- Many proxies are multipurpose proxies
	- HTTP, HTTPS, FTP, etc
## Balancing the load
- Distribute the load
	- Multiple servers
	- Invisible to the end-user
- Large-scale implementations
	- Web server farms, database farms
- Fault tolerance
	- Server outages have no effect
	- Very fast convergence
## Active/active load balancing
- Configurable load - Manage across servers
- TCP offload - Protocol overhead
- SSL offload - Encryption/Decryption
- Caching - Fast response
- Prioritization - QoS
- Content switching - Application-centric balancing
## Active/passive load balancing
- Some servers are active
	- Others are on standby
- If an active server fails, the passive server takes its place
## Sensors and collectors
- Aggregate information from network devices
	- Built-in sensors, separate devices
	- Integrated into switches, routers, servers, firewalls, etc
- Sensors
	- Intrusion prevention systems, firewall logs, authentication logs, web server access logs, database transaction logs, email logs
- Collectors
	- Proprietary consoles (IPS, firewall)
	- SIEM consoles, syslog servers
	- Many SIEMs include a correlation engine to compare diverse sensor data
