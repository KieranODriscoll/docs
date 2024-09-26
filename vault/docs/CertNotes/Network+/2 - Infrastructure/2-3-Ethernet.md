# 2.3 - Ethernet
## Introduction to Ethernet
![](assets/Pasted%20image%2020240919203420.png)
### The MAC address
- Ethernet Media Access Control address
	- The "physical" address of a network adapter
	- Unique to a device
- 48 bits / 6 bytes long
	- Displayed in hexadecimal

- ![](assets/Pasted%20image%2020240919204821.png)
### Duplex
#### Half-duplex
- A device cannot send and receive simultaneously
- All LAN hubs are half-duplex devices
- Switch interfaces can be configured as half-duplex, but usually only when connecting to another half-duplex device
#### Full-duplex
- Data can be sent and received at the same time
- A properly configured switch interface will be set to full-duplex
### CSMA/CD
- CS - Carrier Sense
	- Is there a carrier? Is anyone communicating?
- MA - Multiple Access
	- More than one device on the network
- CD - Collision Detect
	- Collision - Two stations talking at once
	- Identify when data gets garbled
- Half-duplex Ethernet - Not used any longer
- Used for detecting collisions on a network
- is device dependent
	- Device listens for traffic
	- Device transits the traffic
	- Device stops transmitting if collision is detected
- A device is set to listening mode, preventing the device from abruptly sending traffic, device must first ensure that the network path or channel is clear to prevent a collision
- ![](assets/Pasted%20image%2020240919204941.png)
#### CSMA/CD Operation
- Listening for an opening
	- Don't transmit if the network is already busy
- Send a frame of data
	- You send data whenever you can
	- There's no queue or prioritization
- If a collision occurs
	- Transmit a jam signal to let everyone know a collision has occurred
	- Wait a random amount of time, then retry
## Network Switching Overview
### The Switch

- Forward or drop frames
	- Based on the destination MAC address
- Gather a constantly updating list of MAC addresses
	- Builds the list based on the source MAC address of incoming traffic
- Maintain a loop-free environment
	- Using Spanning Tree Protocol (STP)
### Learning the MACs
- Switches examine incoming traffic
	- Make a note of the source MAC address
	- Adds unknown MAC addresses to the MAC address table
		- Sets the output interface to the received interface
### Flooding for unknown Macs
- The switch doesn't always have a MAC address in the table
- When in doubt, send a frame to everyone
### Address Resolution Protocol
- Determine a MAC address based on an IP address
	- You need the hardware address to communicate
- arp -a
	- View local ARP table
### NDP (Neighbor Discovery Protocol)
- No broadcasts
	- Operates using multicast with ICMPv6
- Neighbor MAC discovery
	- Replaces the IPv4 ARP
- SLAAC (Stateless Address Autoconfiguration)
	- Automatically configure an IP address without a DHCP server
- DAD (Duplicate Address Detection)
- Discover routers
	- Router Solicitation (RS) and Router Advertisement (RA)
- Neighbor Solicitation (NS)
	- Sent as Multicast
- Neighbor Advertisement (NA)
- ![](/assets/Pasted%20image%2020240607143138.png)
### Power of Ethernet (PoE)
- Power provided on an ethernet cable
	- One wire for both network and electricity
	- Phones, cameras, wireless access points
	- Useful in difficult to power areas
- Power provided at the switch
	- Built-in power - Endspans
	- In-line power injector - Midspans
- Power modes
	- Mode A - Power on the data pairs
	- Mode B - Power on the spare pairs
### PoE and POE+
#### PoE: IEEE 802.3af-2003
- Original PoE Specification
- Now part of the 802.3 standard
- 15.4 watts DC power
- Maximum current of 350 mA
#### POE+: IEEE 802.3at-2009
- An updated PoE specification
- Now also part of the 802.3 standard
- 25.5 watts DC power
- Maximum current of 600 mA
## VLANs and Trunking
- ![](Pasted%20image%2020240607144336.png)
### LANs
- Local Area Network
	- A group of devices in the same broadcast domain
### Virtual LANs
- Virtual Local Area Networks
	- A group of devices in the same broadcast domain
	- Separated logically instead of physically
### 802.1Q trunking
- Take a normal Ethernet frame
	- ![](Pasted%20image%2020240607143928.png)
- Add a VLAN header in the frame
	- ![](Pasted%20image%2020240607143947.png)
- VLAN IDs - 12 bit long, 4,094 VLANs
	- "Normal range" - 1 through 1005,
	- "Extended range" - 1006 through 4094
	- 0 and 4,095 are reserved VLAN numbers
- Before 802.1Q, there was ISL (Inter-Switch Link)
	- ISL is no longer used
	- Everyone now uses the 802.1Q standard
- Default VLAN of can become populated quickly and affect performance of the VLAN. Overloaded or oversubscribed leading to a reduction in the network performance.
	- Assign the WAN interface to a VLAN with less traffic or its own VLAN
### Working with data and voice
- Old school: Connect computer to switch, connect phone to PBX
	- Two physical cables, two different technologies
- Now: Voice over IP (VoIP)
	- Connect all devices to the Ethernet switch
	- One network cable for both
- Voice and data don't like each other
	- Voice is very sensitive to congestion
	- Data loves to congest the network
- Put the computer on one VLAN and the phone on another
	- But the switch interface is not a truck
- Each switch interface has a data VLAN and a voice VLAN
	- Configure each of them separately
- Configuring a voice and data VLANs
	- Data passes as a normal untagged access VLAN
	- Voice is tagged with an 802.1Q header
## Spanning Tree Protocol
- Builds a loop-free logical topology for Ethernet networks to prevent bridge loops and the broadcast storms resulting from them
- Defined in the 802.1d standard
### Loop Protection
- Connect two switches to each other
	- They'll send traffic back and forth forever
	- There's no "counting" mechanism at the MAC layer
- This is an easy way to bring down a network
	- And somewhat difficult to troubleshoot
	- Relatively easy to resolve
- IEEE standard 802.1D to prevent loops in bridged (switched) networks
- Bridge Protocol Data Unit (BPDU) is used by the Spanning Tree Protocol to prevent the bridge loops.
	- Keeps track of the ports' status on a switch
	- Exchanged between the switches to keep track of the port status
	- If there is an issue with the port or a loop in the network, the port is shutdown
	- Various actions can be performed, blocking it or disabling it
### STP port States
- Blocking - Not forwarding to prevent a loop
- Listening - Not forwarding and cleaning the MAC table
- Learning - No forwarding and adding to the MAC table
- Forwarding - Data passes through and is fully operational
- Disabled - Administrator has turned off the port
### RSTP (802.1W)
- Rapid Spanning Tree Protocol (802.1w)
	- A much-needed updated of STP
	- This is the latest standard
- Faster convergence - From 30 to 50 seconds to 6 seconds
- Backwards-compatible with 802.1D STP
	- You can mix both in your network
- Very similar process - An update, not a wholesale change
### Basic Interface Configuration
- Speed and duplex
	- Speed: 10 / 100 / 1,000 / 10 Gig
	- Duplex: Half/Full
	- Automatic and manual
	- Needs to match on both sides
- IP Address management
	- Layer 3 interfaces. VLAN interfaces
	- Management interfaces
	- IP address, subnet masks/CIDR block, default gateway, DNS (optional)
### VLANs
- VLAN assignment
	- Each device port should be assigned a VLAN
- Trunking
	- Connecting switches together
	- Multiple VLANs in a single link
- Tagged and untagged VLANs
	- A non-tagged frame is on the default VLAN (native VLAN)
	- Trunk ports will tag the outgoing frames
		- and remove the tag on incoming frames
### LAG and mirroring
- Port Bonding / Link aggregation (LAG)
	- Multiple interfaces acts like on big interface
	- LACP (Link Aggregation Control Protocol)
	- Adds additional automation and management
- Port mirroring
	- Copy traffic from one interface
	- Used for packet captures, IDS
	- Mirror traffic on the same switch
	- Mirror traffic from one switch to another
- Examine a copy of the traffic
	- Port mirror (SPAN), network TAP
- No way to block (prevent) traffic
### Link Aggregation Control Protocol (LACP)
- is the 802.3ad protocol and is used to group numerous physical ports to make one high bandwidth path
- Can increase bandwidth and therefore throughput
- Provides network redundancy and load balancing
### Jumbo frames
- Ethernet frames with more than 1,500 bytes of payload
	- Up to 9,216 bytes (9,000 is the accepted norm)
- Increases transfer efficiency
	- Per-packet size
	- Fewer packets to switch/route
- Ethernet devices must support jumbo frames
	- Switches, interface cards
	- Not all devices are compatible with others
- Commonly used in SAN
### Ethernet flow control
- Ethernet is non-deterministic
	- You never know just how fast or slow traffic will flow
- If things get busy, tell the other device to slow down
	- Switches only have so much buffer
- One popular flow control method is IEEE 802.3x
	- The "pause" frame
- Enhancements have been made through the years
	- Incorporate CoS (Class of Service)
### Port Security
- Prevent unauthorized users from connecting to a switch interface - Alert or disable the port
- Based on the source MAC address
	- Even if forwarded from elsewhere
- Each port has its own config - Unique rules for every interface
- Also known as persistent MAC learning or Sticky MAC
- Feature that enables an interface to retain dynamically learned MAC addresses when the switch is restarted or if the interface goes down and is brought back online
- Prevents someone from unplugging their office computer and connecting their laptop to the network without permission since the switch port connected to that network jack would only allow the computer with the original MAC address to gain connectivity
#### Port Security Operation
- Configure a maximum number of source MAC addresses on an interface
	- You decide how many is too many
	- You can also configure specific MAC addresses
- The switch monitors the number of unique MAC addresses
	- Maintains a list of every source MAC address
- Once you exceed the maximum, port security activates
	- Default is to disable the interface
## Straight-Through and Crossover Cables
- ![](Pasted%20image%2020240607151132.png)
### Straight-Through cables
- Patch cables - most common Ethernet cable
- Indicated by the matching of the Tx and Rx pins (pins 1,2,3 and 6) on both sides of the cable
- Connect workstations to network devices
	- Workstation to switch
	- Router to switch
### Ethernet Crossover cables
- Connect MDI to MDI
- Connect MDI-X to MDI-X
- Auto-MDI-X is on most modern Ethernet devices
	- Automatically decides to cross-over
- This is obviously not 568A on one side and 568B on the other
	- These are cabling standards
	- The TIA-568 standard does not define Ethernet (or other) crossover cables
### Straight-through or Crossover
- Workstation to switch
	- Straight-through
- Router to switch
	- Straight-through
- Switch to Switch
	- Crossover
- Router to router
	- Crossover
- Workstation to workstation
	- Crossover
- Workstation to router
	- Crossover


