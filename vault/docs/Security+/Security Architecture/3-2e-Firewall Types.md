# 3.2e - Firewall Types
## The Universal Security Control
- Standard issue
	- Home, office, and in your operating system
- Control the flow of network traffic
	- Everything passes through the firewall
- Corporate control of outbound and inbound data
	- Sensitive materials
- Control of inappropriate content
	- Note safe for work, parental controls
- Protection against evil
	- Anti-virus, anti-malware
## Network-based firewalls
- Filter traffic by port number or application
	- OSI layer 4 vs OSI layer 7
	- Traditional vs NGFW firewalls
- Encrypt traffic
	- VPN between sites
- Most firewalls can be layer 3 devices (routers)
	- Often sits on the ingress/egress of the network
	- Authenticate dynamic routing communication
## UTM / All-in-one security appliance
- Unified Threat Management (UTM)
	- Web security gateway
- URL filter / Content inspection
	- Malware inspection
- Spam filter
	- CSU/DSU
- Router, Switch
	- Firewall
- IDS/IPS
	- Bandwidth shaper
	- VPN endpoint
## Next-generation firewall (NGFW)
- The OSI Application layer
	- All data in every packet
- Can be called different names
	- Application Layer gateway
	- Stateful multilayer inspection
	- Deep packet inspection
- Requires some advanced decodes
	- Every packet must be analyzed and categorized before a security decision is determined
- Network-based firewalls
	- Control traffic flows based on the application
- Intrusion Prevention SYstems
	- Identify the application
	- Apply application-specific vulnerability signatures to the traffic
- Content filtering
	- URL filters
	- Control website traffic by category
## Web application firewall (WAF)
- Not like a "normal" firewall
	- Applies rules to HTTP/HTTPS conversations
- Allow or deny based on expected input
	- Unexpected input is a common method of exploiting an application
- SQL injection
	- Add your own commands to an application's SQL query
- A major focus of Payment Card Industry Data Security Standard (PCI DSS)