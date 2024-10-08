# 5.5 - Network Troubleshooting
## General Network Troubleshooting
### Device configuration review
- Don't start blindly troubleshooting
	- Know what you're getting into
- View the configuration
	- Native desktop or web-based console
	- SSH/terminal console
- Try getting the configuration ahead of time - Prepare early
### Routing tables
- The digital version of asking for directions
	- Know how to get from point A to point B
- This can answer a lot of questions
	- Default gateway, manually configured static routes
- Know which way data will flow
	- A network map might help
- Refer to every router
	- Routing loops and missing routes are common
		- Maximum hop count and TTL help prevent routing loops
### Interface status
- Know the details of the important interfaces
	- Easy to view on the console
	- You'll rarely be physically next to the device
- Check the easy stuff firest
	- Verify the physical connectivity
	- Nothing works properly if the interface is misconfigured
- You will often solve the problem here
	- Check for errors and mismatches
	- It's a quick and easy fix
### VLAN assignment
- Network link is active and
	- IP address is assigned
	- No access to resources or limited functionality
- Every switch interface is configured as an access port or a trunk port
	- Each access port is assigned to a VLAN
- Confirm the specific switch interface
	- Check the VLAN assignment
- This is also a common issue
	- Another quick fix
### Network performance baseline
- Troubleshooting starts with a blank slate
	- A baseline can add context
- Intermittent or all-day issues
	- Check utilization, individual device performance, etc
- Some organizations already collect this data
	- Check the SIEM or management console
- Look for patterns and correlation
	- The baseline might also tell you what's NOT happening
## Common Network Issues
### Half-duplex Ethernet
- If two devices communicate simultaneously, you have collision
### Collisions
- On a half-duplex link, collisions are normal
	- Heavy utilization, can cause excessive collisions
- Most Ethernet connections are full-duplex
	- Where are the collisions coming from?
- Interface configuration issues
	- Duplex mismatch
- Hardware issues
	- Could indicate a bad NIC or bad driver
### Broadcast storms
- Some processes use broadcasts to communicate
	- Send a message to every device
- Broadcast domain
	- A single VLAN
	- Broadcast domains are separate by routers
- Large numbers of broadcasts can impact performance
	- Each device must process every broadcast
#### Troubleshooting broadcast storms
- Packet capture
	- Identify the source
- Research the process that's broadcasting
	- There may be another option
- Separate the network into smaller broadcast domains
	- Change one large subnet to many smaller routed subnets
### Duplicate MAC addresses
- Not a common occurrence
	- MAC address are designed to be unique
	- May be an on-path attack
- Mistakes can happen
	- Locally administered MAC addresses
	- Manufacturing error
- Intermittent connectivity
	- Confirm with a packet capture, should see ARP contention
- Use the ARP command from another computer
	- Confirm the MAC matches the IP
### Duplicate IP addresses
- Static address assignments
	- Must be very organized
- DHCP isn't a panacea
	- Static IP addressing
	- Multiple DHCP servers overlap
	- Rogue DHCP servers
- Intermittent connectivity
	- Two addresses "fight" with each other
- Blocked by the OS
	- Checks when it starts
#### Troubleshooting duplicate IP addresses
- Check your IP addressing
	- Did you misconfigure?
- Ping an IP address before static addressing
	- Does it respond?
- Determine the IP addresses
	- Ping the IP address, check your ARP table
	- Find the MAC address in your switch MAC table
- Capture the DHCP process
	- What DHCP servers are responding
### Mutlicast flooding
- Multicast
	- Used for one-to-many traffic flows
	- For example, live video feeds
- Switches forward multicast traffic
	- There's no multicast destination address in the switch forwarding table
	- All multicast traffic is sent to every switch port
	- Multicast flooding
- Every device receives the multicast traffic
	- Consumes resources on the remote device
	- Uses bandwidth and switch processing time
### IGMP Snooping
- IGMP (Internet Group Management Protocol)
	- Hosts and routers use IGMP to direct multicast transmissions
	- Used for multicasting
- Switches can watch for these IGMP messages
	- The switch then intelligently forwards multicasts to those specific devices
	- Enable IGMP snooping
### Asymmetric routes
- Traffic follow one path on egress
	- And a different path on ingress, or vice versa
	- This is often by design
- This can be difficult to troubleshoot
	- It may be challenging to understand the path
- Firewalls may drop sessions
	- An unexpected traffic flow is dropped by default
- Traceroute can help
	- Identify potential asymmetric routes
### Switching loops
- Router A thinks the next hop is to Router B
	- Router B thinks the next hop is router A
	- and repeat until TTL = 0
- Easy to misconfigure
	- Especially with static routing
- A traceroute will tell the story
	- Check the routing tables in each L3 device
	- Modify routing tables as needed
### Missing route
- A route to the destination network does not exist
	- The packet will be dropped
- ICMP host unreachable message will be sent to the source address
	- Source device will be informed of the error
- Check your routes
	- In both directions
### Rogue DHCP server
- IP addresses assigned by a non-authorized server
	- There's no inherent security in the DHCP
- Client is assigned an invalid or duplicate address
	- Intermittent connectivity, no connectivity
- Disable rogue DHCP communication
	- Enable DHCP snooping on your switch
	- Authorized DHCP servers in Active Directory
- Disable the rogue
	- Renew the IP leases
### Exhausted DHCP scope
- Client received an APIPA address
	- Local subnet communication only
- Check the DHCP server
	- Add more IP addresses if possible
- IP address management (IPAM) may help
	- Monitor and report on IP address shortages
- Lower the lease time
	- Especially if there are a lot of transient users
### IP configuration issues
- Communicate to local IP addresses
	- But not outside subnets
- No IP commuincation
	- Local or remote
- Communicate to some IP addresses
	- But not others
- Communicate to some IP addresses
	- But not others
#### Troubleshooting IP configurations
- Check your documentation
	- IP address, subnet mask, gateway, DNS
- Monitor the traffic
	- Examine local broadcasts
	- Difficult to determine subnet mask
- Check devices around you
	- Confirm your subnet mask and gateway
- Traceroute and ping
- The issue might be your infrastructure
- Ping local IP, default gateway, and outside address
### Low optical link budget
- Fiber networks rely on the transmission of light
	- Block the light, block the network
- Attenuation
	- A challenge over long distances
	- Or with dirty connectors
- Always check with a light meter
	- Equipment documentation will specify the required amount of light
### Certificate issues
- Security alerts and invalid certificates
	- Something isn't quite right
	- Should raise your interest
- Look at the certificate details
	- Click the lock icon
	- May be expired or the wrong domain name
	- The certificate may not be properly signed (untrusted certificate authority)
	- Correct time and date is important
### Hardware failures
- No response
	- Application doesn't response
- Confirm connectivity
	- Without a ping, you're not going to connect
- Run a traceroute
	- See if you're being filtered
	- Should make it to the other side
- Check the server
	- Lights? Fire?
### Incorrect firewall setting
- Applications not working
	- Based on the application in use or the protocol and port
- Check the host-based firewall settings
	- Accessibility may be limited to an administrator
	- Managed from a central console
- Confirm the network-based firewall config
	- Check the policy list and logs
- Take a packet capture
	- The traffic may never make it to the network
	- Dropped by the operating system
### Incorrect VLAN configurations
- Check VLAN assignments on the switch
	- This is one of the most common issues you'll find
- Confirm the data and voice VLAN assignments
	- Useful when using VoIP phones
- Validate the physical interface with the VLAN number
	- Also important for trunks
### DNS issues
- Web browsing doesn't work
	- The internet is broken
- Ping works, browser doesn't
	- There isn't a communication problem
- Applications aren't communicating
	- They often use names and not IP addresses
#### Troubleshooting DNS issues
- Check your IP configuration
	- Is the DNS IP address correct
- Use nslookup or dig to test
	- Does the resolution work?
- Try a different DNS server
	- Google is 8.8.8.8
	- Quad9 is 9.9.9.9
### NTP Issues
- Some cryptography is very time sensitive
	- Active Directory requires clocks set within five minutes of each other
- Kerberos communication use a time stamp
	- If the ticket shown during authentication is too old, it's invalid
- Client can't login
	- Check the timestamp of the client and the server
- Configure NTP on all devices
	- Automate the clock setting
### BYOD
- Bring your own device
- Employee owns the devices
	- Needs to meet the company's requirements
- Difficult to secure
	- It's both a home device and a work device
	- How is data protected?
	- What happens to the data when a device is sold or traded in?
- Use an MDM (Mobile Device Manager)
### Licensed feature issues
- Featured are often individually licensed
	- Requires payment or some type of license agreement
- Some features may not be available
	- A license key unlocks functionality
- This can cause problems during an upgrade or configuration update
	- Test your changes in the lab
### Network performance issues
- There's never just one performance metric
	- A series of technologies working together
- I/O bus, CPU speed, storage access speed, network throughput, etc
	- One of these can slow all of the others down
- You must monitor all of them to find the slowest one
	- This may be more difficult than you might expect
