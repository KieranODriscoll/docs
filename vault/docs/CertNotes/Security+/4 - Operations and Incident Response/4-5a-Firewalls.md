# 4.5a - Firewalls
## Network-based firewalls
- Filter traffic by port number or application
	- Traditional vs NGFW
- Encrypt traffic
	- VPN between sites
- Most firewalls can be layer 3 devices (routers)
	- Often sits on the ingress/egress of the network
	- Network Address Translation (NAT)
	- Dynamic routing
## Next-generation Firewalls (NGFW)
- The OSI Application Layer
	- Layer 7 firewall
- Can be called different names
	- Application layer gateway
	- Stateful multilayer inspection
	- Deep packet inspection
- Requires some advanced decodes
	- Every packet must be analyzed, categorized, and a security decision determined
## Ports and protocols
- Make forwarding decisions based on protocol (TCP or UDP) and port number
	- Traditional port-based firewalls
	- Add to an NGFW for additional security policy options
- Based on destination protocol and port
	- Web server: TCP/80, TCP/443
	- SSH server: TCP/22
	- Microsoft RDP: TCP/3389
	- DNS query: UDP/53
	- NTP: UDP/123
## Firewall rules
- A logical path
	- Usually top-to-bottom
- Can be very general or very specific
	- Specific rules are usually at the top
- Implicit deny
	- Most firewalls include a deny at the bottom
	- Even if you didn't put one
- Access control lists (ACLs)
	- Allow or disallow traffic
	- Groupings of categories
	- Source IP, Destination IP, port number, time of day, application, etc
## Screened subnet
- An additional layer of security between the you and the Internet
	- Public access to public resources
	- Private data remains inaccessible
## IPS rules
- Intrusion Prevention System
	- Usually integrated into an NGFW
- Different ways to find malicious traffic
	- Look at traffic as it passed by
- Signature-based - Look for a perfect match
- Anomaly-based
	- Build a baseline of what's "normal"
	- Unusual traffic patterns are flagged
- You determine what happens when unwanted traffic appears
	- Block, allow, send an alert, etc
- Thousands of rules - Or more
- Rules can be customized by group
	- Or as individual rules
- This can take time to find the right balance
	- Security / alert "noise" / false positives