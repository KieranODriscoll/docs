# 1.4 - IP Addressing
## Binary Math
![](Pasted%20image%2020240604111444.png)
## IPv4 Addressing
### Networking with IPv4
- IP address, unique for every device
- Subnet mask
	- Used by the local device to determine what subnet its on
	- The subnet mask isn't (usually) transmitted across the network
	- You'll ask for the subnet mask all the time
- Default gateway
	- The router that allows you to communicate outside of your local network
	- The default gateway must be an IP address on the local subnet
### Special IPv4 addresses
- Loopback address
	- An address to yourself
	- Ranges from 127.0.0.1 through 127.255.255.254
	- An easy way to self-reference (ping 127.0.0.1)
	- Default gateway must be an IP address on the local subnet
- Reserved addresses
	- set aside for future use or testing
	- 240.0.0.1 through 254.255.255.254
- Virtual IP Addresses (VIP)
	- No associated with a physical network adapter
	- Virtual machine, internal router address
### DHCP
- IPv4 address configuration used to be manual
	- IP address, subnet mask, gateway, DNS servers, NTP servers, etc
- Dynamic Host Configuration Protocol
	- Provides automatic addresses and IP configuration for almost all devices
### APIPA - Automatic Private IP Addressing
- A link-local address - No forwarding by routers
- IETF has reserved
	- 169.254.0.1 through 169.254.255.254
	- First and last 256 addresses are reserved
	- Functional block of 169.254.1.0 through 169.254.254.255
- Is an IP address assigned to a system when the DHCP server is not available
- Is not a routable IP address
## Network Address Translation (NAT)
- It is estimated that there are over 20 billion devices connected to the internet
	- IPv4 supports around 4.29 billion devices
- The address space for IPv4 is exhausted
	- There are no available addresses to assign
- ![](Pasted%20image%2020240604112956.png)
- IP addresses assigned to devices are either public or private
- An organization use private IP addresses for the internal systems and public IP addresses for the exposed system on the Internet
- Private IP addresses are for internal systems only
	- Concept is described in RFC 1918
- ![](Pasted%20image%2020240604113138.png)
- ![](Pasted%20image%2020240604113148.png)
- Allows the internal hosts to communicate on the internet
- Enables several internal IP addresses to use a single public IP address
- Can be configured on a firewall, router or dedicated device
### Port Address Translation (PAT)
- Type of NAT configuration
- Is also known as overloading that uses dynamic NAT
- Uses IPv4 addresses along with the port numbers
- Maps private IP addresses to a single public IP address
	- Uses different ports
	- Performs many-to-one configuration
## Network Communication
### Unicast
- One station sending information to another station
- Send information between two systems
- Web surfing, file transfer
- Does not scale optimally for streaming media
- ![](Pasted%20image%2020240604113525.png)
- Comprises two parts:
	- 64-bit network prefix that is used for routing
	- 64-bit interface identifier that is used for identifying a host computer's network interface
- Link Local
	- is a unicast address
	- Is used for communication by nodes that exist on the same link
	- Is equivalent to Automatic Private IP Addressing IPv4 Address
	- Is limited to the local link
	- Is used by the Neighbor Discovery processes
	- Begins with FE80
	- Not routable
### Broadcast
- Send information to everyone at once
- One packet, received by everyone
- Limited scope - the broadcast domain
- Routing updates, ARP requests
- Not used in IPv6 - focus on multicast
- ![](Pasted%20image%2020240604113725.png)
### Multicast
- Delivery of information to interested systems
	- One to many
- Multimedia delivery, stock exchanges
- Very specialized
	- difficult to scale across large networks
- Used in both IPv4 and IPV6
	- Extensive use in IPv6
- ![](Pasted%20image%2020240604114349.png)
- ![](Pasted%20image%2020240619111710.png)
- Starts with FF or 1111 1111 prefix
- Multicast is never a source address but defines a destination
- Multicast is a TCP/IP technology that sends out the packets to the requested devices when streaming to multiple workstations from a single streaming media server. 
- As opposed to broadcast (one-to-all), which sends out packets to all devices, multicast (one-to-many-of-many/many-to-many-of-many) only sends packets to the clients that specifically requested to be a part of the distribution and not just every client on the network. 
- Multicast requires the proper implementation and configuration to route the traffic to the right devices on the LAN so that streaming can properly function. Multicast works with IPv4 or IPv6.
### Anycat
- Single destination IP address has multiple paths to two or more endpoints
	- One to one of many
	- Used in IPv4 and IPv6
- Configure the same anycast address are delivered on different devices
	- Looks like any other unicast address
- Packets sent to an anycast address are delivered to the closest interface
	- Announce the same route out of multiple data centers, clients use the data center closest to them
	- Anycast DNS
- Works like a multicast address, however, delivered only to one address, the closest IPv6 address
## Classful Subnetting and IPv4 Subnet Masks
- ![](Pasted%20image%2020240604115152.png)
	- must subtract 2 networks from # of networks, 0.0.0.0 and 127.0.0.1 as they can't be allocated
### Classful Subnetting
- Very specific subnetting architecture
	- not used since 1993 but still referenced in casual conversation
- Used as a starting point when subnetting
	- standard values
### The construction of a subnet
- Network address
	- The first IP address of a subnet - set all host bits to 0 (0 decimal)
- First usable host address
	- One number higher than the network address
- Network broadcast address
	- The last IP address of a subnet - Set all host bits to 1 (255 decimal)
- Last Usable host address
	- One number lower than the broadcast address
## Calculating IPv4 Subnets and Hosts
### VLSM (Variable Length Subnet Masks)
- Class-based networks are inefficient
	- The subnet mask is based on the network class
- Allow network admins to define their own masks
	- Customize the subnet mask to specific network requirements
- Use different subnet masks in the same classful network
	- 10.0.0.0/8 is the Class A network - 10.0.1.0/24 and 10.0.8.0/26 would be VSLM
- Number of subnets = 2<sup>subnet bits</sup>
- Hosts per subnet = 2<sup>host bits - 2</sup>
![](Pasted%20image%2020240604120656.png)
Subnet mask:
	- Determine if a host is on the same network or not
	- is a 32-bit address
- Variable-length Subnet Mask (VLSM)
	- Allows subnets to be variable in size
	- Allow hosts to be variable in numbers in each subnet
	- Uses only classless routing protocols
	- Uses different configurations for different subnet masks
	- Mainly used for IPv4 public IP addresses
### Classless Inter-Domain Routing (CIDR) Notation
- Is used for allocation of IP addresses
- Is based on VLSM
- Breaks the IP address into two parts
	- Network address: is used as a prefix
	- Remaining address: is used as a suffix with the number of bits remaining in the address
- Overall improves the efficiency of IPv4 allocation without wasting IP addresses
- ![](Pasted%20image%2020240619120829.png)
### Magic Number Subnetting
### Four important addresses
- Network address / Subnet ID
	- First address in the subnet
- Broadcast address
	- Last address in the subnet
- First available host address
	- One more than network address
- Last available host address
	- One less than the broadcast address
### Magic number subnetting
- Very straightforward method, can perform the math in your head
- Subnet with minimal math
- Some charts might help
	- CIDR to Decimal
	- Host ranges
### The magic number process
- Convert the subnet mask to decimal
- Identify the "interesting octet"
- Calculate the "magic number"
	- 256 minus the interesting octet
	- Calculate the host range
- Identify the network address
	- First address in the range
- Identify the broadcast address
	- Last address in the range
- ![](Pasted%20image%2020240604121142.png)
### Seven Second Subnetting
- Convert IP Address and subnet mask to decimal
	- Use chart to convert between CIDR-block notation and decimal
	- Same chart also shows the umber of devices per subnet
	- ![](Pasted%20image%2020240604121417.png)
- Determine network/subnet address
	- Second chart shows the starting subnet boundary
- Determine broadcast
	- Chart below shows the ending subnet boundary
- Calculate first and last usable IP address
	- Add one from network address, subtract one from broadcast address
- ![](Pasted%20image%2020240604121557.png)
## IPv6 Addressing
- Internet Protocol V6 - 128 Bit Address
- 340 undecillion
- DNS comes very important
- Group of zeros can be abbreviated with a double colon ::
	- Only one of these abbreviations allowed per address
	- Leadings zeros are option
- ![](Pasted%20image%2020240605163516.png)
### Configuring IPv6 with a modified EUI-64
- Static addressing can be useful
- Extended Unique Identified (64-bit)
- Combined a 64 bit IPv6 prefix and the MAC address
- Need some extra bits
### Converting EUI-48 to EUI-64
- Split the MAC
	- Two 3 byte halves
- Put FFFE in the middle
	- The missing 16 bits above
- Invert the seventh bit
	- Changes the address from globally unique/universal
	- Turns the burned-in address (BIA) into a locally administered address
	- This is the U/L (universal/local)
### Shortcut for flipping the 7th bit
- Quickly convert the MAC address - create a chart
- Convert 0 to F in hex, two columns, group of four
- Quickly convert the second character of the first hex byte
- ![](Pasted%20image%2020240605164005.png)
- ![](Pasted%20image%2020240605164015.png)
## IPv6 Subnet Masks
- Assigning IPv6 Addresses
	- Internet Assigned Numbers Authority (IANA) provides address blocks to RIRs (Regional Internet Registries)
	- RIRs assigns smaller subnet blocks to ISPs
	- ISP assigns a /48 subnet to the customer
- ![](Pasted%20image%2020240605164136.png)
## Configuring IPv6
### Tunneling IPv6
- 6 to 4 addressing
	- Send IPv6 over an existing IPv4 network
	- Creates an IPv6 based on the IPv4 address
	- Requires a relay router
	- No support for NAT
- 4in6 - Tunnel IPv4 traffic on an IPv6 network
- Encapsulating the IPv6 packets with an IPv4 header
- Allows the IPv6 packets to be sent to an IPv4 network
- Sets the protocol field to 41 indicative of an encapsulated IPv6 packet
	- Source field: IPv4 address
	- Destination field: IPv4 address
- Need to configure the tunnel endpoints manually or automatically
- 
### Teredo/Miredo
- Tunnel IPv6 through NATed IPv4
	- End-to-end IPv6 through an IPv4 network
	- No special IPv6 router needed
	- Temporary use
- Miredo - Open-source Teredo for Linux
- BSD Unix, Mac OS X full functionality
### Dual-stacking routing
- Dual-stack IPv4 and IPv6 - Run both at the same time
	- Interfaces will be assigned multiple address types
- IPv4
	- Configured with an IPv4 addresses
	- Maintains an IPv4 routing table
	- Uses IPv4 dynamic routing protocols
- IPv6
	- Configured with IPv6 addresses
	- Maintains a separate IPv6 routing table
	- Uses IPv6 dynamic routing protocols
- Is a migration stategy
- Allows the devices and applications to be configured with IPv4 and IPv6
- Requires gradual movement to the IPv6
- ![](Pasted%20image%2020240619121932.png)
### Neighbor Solicitation
- There is no ARP in IPv6
- Neighbor solicitation (NS) - Sent as a multicast
- Neighbor advertisement (NA)
### NDP (Neighbor Discovery Protocol)
- No Broadcasts - operates using multicast on ICMPv6
- Neighbor MAC Discovery - Replaces IPv4 ARP
- SLAAC (Stateless Address Autoconfiguration)
	- Automatically configure an IP address without a DHCP server
	- Assigns a network device with a link-local unicast address and a global unicast address
	- Uses the prefix information from the router and appends the MAC address of the device using NDP
	- ![](Pasted%20image%2020240619122706.png)
	- Process:
		1. The host sends a Router solicitation message in a multicast message to all routers
		2. Upon receiving the multicast message, the router responds with the prefix information using the Router Advertisement, also a multicast message
		3. After receiving the prefix information, the host generates the IP address, which is an IPv6 address. It uses the prefix and its own MAC address
		4. The host performs the duplicate address detection process
		5. If no positive outcome of DAD, then the newly generated IP address is marked as tentative
		6. Finally, the address is allocated to the host
- DAD (Duplicate Address Detection) - No Duplicate IPs
- Discover Routers
	- Router solicitation (RS) and router advertisement (RA)
- Router Advertisement Guard
	- Provides support for allowing network administrators to block or reject unwanted or rogue router advertisement guard messages that arrive at the network device platform
#### Router Advertisement
- Is sent by the router to provide network ID to the hosts
- Is a response to Router solicitation message
- ![](Pasted%20image%2020240619122524.png)
- Router itself does not initiate the process, a host initiates
- Host sends a Router Solicitation message to all routers and receives the Router Advertisement
### Finding Router
- ICMPv6 adds the Neighbor Discovery Protocol
- Routers also send unsolicited RA messages
	- From the multicast destination of ff02::1
- Transfers IPv6 address information, prefix value, and prefix length, etc - sent as a multicast
- Neighbor Advertisement (NA)
## Virtual IPs (VIPs)
- Is substitution of a public IP address with private IP addresses of a NIC
- Is the public IP address that is not assigned to the NIC
- Can be configured with NAT using routers or firewall
- Can be a public IP address not assigned to the physical NIC in a system or a networking device but is used to represent the system
- When traffic is sent to the public IP address, it is further distributed to the actual IP addresses assigned to the physical NIC.
- One example of NAT
- Another example is the Virtual IP can be the IP address of the load balancer, uses the load balancers IP to connect, load balancer distributed the traffic down further based on load.
- ![](Pasted%20image%2020240619125225.png)
### Subinterfaces
- Divide a single physical NIC into two or more interfaces
- Is a virtual interface that is part of the physical interface
- Is configured like a physical interface
- Example:
	- A cisco router with one physical NIC that is divided into two subnets for routing the data.
- ![](Pasted%20image%2020240619125350.png)