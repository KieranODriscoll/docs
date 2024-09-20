# 1.2 - Networks
## Network Topologies
- Useful in planning a new network
	- physical layout of building
- Assists in understanding signal flow
	- helps troubleshooting issues
### Star
- Hub and Spoke
- Used in most large and small networks
- One of the most popular topologies
- All devices are connected to a central device
- Switched Ethernet networks
	- The switch is in the middle
- ![](Pasted%20image%2020240522131653.png)
- Provides the ease of adding or removing devices
- If a node fails, then it does not impact the network
- If the switch fails then the entire network goes down
### Ring
- Used in many popular topologies
- Used quite often in WAN
- Still used in MANs (Metro Area Network) and WANs
- Creates additional redundancies using this topologies
- Dual-rings
- Built-in fault tolerance, if one link is severed, data will go around the ring until it can't and then sent back around the ring if it can't complete the routing
- ![](Pasted%20image%2020240522131944.png)
- If ring is unidirectional, data only travels one direction, an impact affects the entire network
### Bus
- Early local area networks
	- coaxial cable was the bus
- Simple, but prone to errors
	- One break in the link disabled the entire network
- Controller Area Network
	- CAN Bus
	- Automotive
		- Connecting all the sensors together
- ![](Pasted%20image%2020240522132301.png)
- Single backbone to which the devices connect
- Used in small networks
- Hard to troubleshoot and add more devices
	- Hard to troubleshoot an issue if the network is down
- If backbone is broken it can divide the network or fail entirely
### Mesh
- Multiple links to the same place
	- Fully connected (mesh) - each node is connected to other nodes in the network
	- Partially connected
	- half mesh - node is connected to a minimum of two nodes
- Redundancy, fault-tolerant, load balancing
- Used in WANs
	- fully meshed or partially meshed
- ![](Pasted%20image%2020240522132447.png)
- Each node is connected to the other nodes on the network
- Several paths to transmit data, if one becomes unavailable, it can be sent through a different path.
- Unavailability of one node does not impact the rest of the network, nor does adding or removing a node
- Number of nodes formula: n(n-1) / 2 and this will give the number of connections
### Hybrid
- A combination of one or more physical topologies
	- Most networks are hybrid
- ![](Pasted%20image%2020240522132500.png)
## Wireless Topologies
- Infrastructure
	- All devices communicate through an access point
	- The most common wireless communication mode
- Ad hoc networking
	- No pre-existing infrastructure
	- Devices communication amongst themselves
- Mesh
	- Ad hoc devices work together to form a mesh "cloud"
	- Self form and self heal
	- IOT Devices
## Network Types
### Peer-to-peer
- All devices are both clients and servers
	- Everyone talks to everyone
- Advantages
	- Easy to deploy, low cost
- Disadvantages
	- difficult to administer
	- difficult to secure
- ![](Pasted%20image%2020240528135944.png)
- Considers every device with same privileges
- Every device is a peer to to the others
- Works well with a small network
- Each node is responsible for its own security
### Client - Server
- Central server, centralized authority
	- Clients talk to the server
	- Server is the controlling authority
- No client-to-client communication
- Advantages
	- Performance, administration
- Disadvantages
	- Cost, complexity
- ![](Pasted%20image%2020240528140041.png)
- Can be used for various purposes, such as authentication
- Unavailable when server goes down

![](Pasted%20image%2020240528155941.png)
### LAN - Local Area Network
- A building or group of buildings
	- High-speed connectivity
- Ethernet and 802.11 wireless
	- Any slower and it isn't "local"
### MAN - Metropolitan Area Network
- A network in your city
- Larger than a LAN, often smaller than a WAN
- Common to see government ownership
### WAN - Wide Area Network
- Generally connects LANs across a distance
- Generally much slower than a LAN
- Many different WAN technologies
	- Point-to-point serial, MPLS, etc
	- Terrestrial and non-terrestrial
### WLAN - Wireless LAN
- 802.11 technologies
- Mobility within a building or geographical area
- Expand coverage with additional access points
- Wireless network with several devices connected to it
- Works like a wired ethernet network
- Configured in home or offices, usually
- Two modes:
	- Infrastructure
		- Wireless access point, can be further configured to use authentication
	- Peer-to-peer (independent)
		- Mobile hotspot
- Controls access to a shared transmission medium using CSMA/CA
	- Used in wireless networks
	- CSMA/CD used in ethernet networks
	- Carrier-sense multiple access with collision avoidance
### PAN - Personal Area Network
- Your own private network
- Bluetooth, IR, NFC
- Automobile
	- Audio Output
	- Integrate with Phone
- Mobile Phone
	- Wireless headset
- Health
	- Workout telemetry, daily reports
- Connects various devices such as:
	- System
	- Gaming console
	- Mobile
	- Tablet
	- Printer
- Is limited within 10 meters
- Can be a combo of wireless and wired
- PAN has distance limitations dependent on the length of the wires used to connect devices with the systems. You can have wired and wireless devices, which are also limited within the range of wireless connectivity.
### CAN - Campus Area Network
- Corporate Area Network
- Limited geographical area, group of buildings
- LAN technologies
	- Fiber connected, high speed ethernet
- Your fiber in the group, no third-party provider
- Interconnects various LANs
- Smaller than a MAN but bigger than a LAN
- Combo of both wired and wireless networks
### NAS vs SAN
- Network Attached Storage  (NAS)
	- Connect to a shared storage device across the network
	- File-level access
- Storage Area Network (SAN)
	- looks and feels like a local storage device
	- Block-level access
	- Very efficient reading and writing
	- Segregates the traffic from typical LAN traffic
	- Uses protocols such as Fiber channel and iSCSI
	- Helps to increase storage utilization and security 
- Requires lots of bandwidth
	- May use an isolated network and high-speed network
### MPLS - Multiprotocol Label Switching
- Learning from ATM and Frame Relay
- Packets through the WAN have a label
	- Routing decisions are easy
- Labels are defined in the data headers
- Labels are nothing more than numbers assigned to the data that needs to be transported
- Labels can allow data prioritization
- Any transport medium, any protocol inside
	- IP Packets, ATM cells, Ethernet Frames
	- OSI layer 2.5 (!)
- Increasingly common WAN technology
	- Ready-to-network
- MPLS Pushing and Popping
	- Labels are pushed onto a packet as they enter the MPLS cloud
	- Labels are popped off on the way out
- Speeds up the network traffic without executing complex routing queries
- ![](Pasted%20image%2020240528150011.png)
- Characteristics of MPLS
	- Used for connecting devices on a WAN
	- Unencrypted network traffic
	- Enables sending packets over a single, faster network path (routing decisions based on labels)
	- Enables delivery of various data packets types over the same network link
### mGRE
- Multipoint Generic Router Encapsulation
	- Used extensively for Dynamic Multipoint VPN (DMVPN)
	- Common on cisco routers
- Enables one to multi node communication
- Your VPN builds itself
	- Remote sites communicate to each other
- Tunnels are built dynamically, on-demand
	- A dynamic mesh
- Removes the bottleneck of configuring static endpoints by enabling dynamic connections
- One of the core uses of mGRE is in the Dynamic Multipoint VPN deployments, in which you do not have to pre-configure the endpoints for VPN connectivity. The mGRE protocol uses dynamic connections that create the VPN connections, and in the end, it terminates those connections
- Protocol that can used to enable one node to communicate with many nodes by encapsulating layer 3 protocols to create tunnels over another network
- Often used Dynamic Multipoint VPN (DMVPN) connections
- Features:
	- Point-to-multipoint network links
	- Tunneling protocol
	- Enables delivery of various data packet types over the same network link
	- Used in Dynamic Multipoint VPN (DMVPN)
### SD-WAN
- Software defined networking in a WAN
	- A WAN built for the cloud
- The data center used to be in one place
	- The cloud has changed everything
- Cloud-based applications communicate directly to the cloud
	- No need to hop through a central point
- ![](Pasted%20image%2020240528150424.png)
- Integrates various protocols, such as MPLS and LTE
- Can make real-time changes without impacting the existing functionality
- ![](Pasted%20image%2020240528161201.png)
- Uses software to manage devices and services running over the WAN, instead of having to manage each one individually
- Decouples underlying hardware from its control methods
## WAN Termination
### Demarcation point
- The point where you connect with the outside world
	- WAN provider
	- Internet service provider
	- The demarc
- The hand-off point from one entity to another entity
	- leased line to organization
	- Point where responsibility of the equipment switches
- Used everywhere
	- Even at home
- Central location in a building
	- Usually a network interface device
	- Can be as simple as an RJ-45 connection
- You connect your CPE
	- Customer premise equipment or "customer prem"
### Smartjack
- The equipment for terminating a connection
- Network Interface Unit (NIU)
	- The device that determines the demarc
	- Network Interface Device, Telephone Network Interface
- Smartjack
	- More than just a simple interface
	- Can be a circuit card in a chassis
- Build-in diagnostics
	- Loopback tests
- Alarm indicators
	- Configuration, status
## Virtual Networks
- Server farm with 100 individual computers
	- It's a big farm
- All servers are connected with enterprise switches and routers
	- with redundancy
- Migrate 100 physical servers to one physical server
	- With 100 virtual servers inside
- What happens to the network?
### Network function virtualization (NFV)
- Replace physical network devices with virtual versions
	- Manage from the hypervisor
- Same functionality as a physical device
	- Routing, switching, load balancing, firewalls, etc
- Virtualizes the network services:
	- Firewall, Router, Switches
- Decouples the networking services from the hardware and virtualizes them
- Quickly and easily deploy network functions
	- Click and deploy from the hypervisor
- Many difference deployment options
	- Virtual machine, container, fault tolerance, etc
- Like a typical physical network, a virtual network also has various networking devices or services like switches, firewalls, and routers. NFV or Network Function Virtualization is a method of virtualizing these services and making them work in the virtual environment. There is no dependency on the hardware appliances or devices because NFV enables them to run in the virtual environment
- ![](Pasted%20image%2020240528163010.png)
### The hypervisor
- Virtual Machine Manager
	- Manages the virtual platform and guest operating systems
- Virtualizes hardware for virtual machines
- Hardware management
	- CPU, networking, security, RAM, other physical resources
- Single console control
	- One pane of glass
- 2 types of hypervisor:
	- Type 1 - bare metal or native
	- Type 2 - hosted hypervisors
### vSwitch
- Virtual switch
	- Move the physical switch into the virtual environment
- Functionality is similar to a physical switch
	- Forwarding options, link aggregation, port mirroring, NetFlow
- Emulates the layer-2 switch
- Does not work with:
	- MAC address
	- Spanning Tree Protocol
	- Creates a network loop for redundancy
- Deploy from the hypervisor
	- Automate with orchestration
### Virtual Network Interface Card (vNIC)
- A virtual machine needs a network interface
- Uses the same sequences as Ethernet adapters:
	- Eth0 as vnic0
	- Eth1 as vnic1
- Connects to the virtual switch
- Configure and connected through the hypervisor
	- Enable additional features
	- VLAN, aggregation, multiple interfaces
- ![](Pasted%20image%2020240528162818.png)
## Provider Links
### Satellite networking
- Communication to a satellite
	- Non-terrestrial communication
- High cost relative to terrestrial networking
	- 50 Mbit/s down, 3 Mbit/s up are common
	- Remote sites, difficult-to-network sites
- High latency
	- 250ms up, 250 ms down
- High frequencies - 2 GHz
	- Line of sight, raid fade
### Copper
- Extensive installations
	- Relatively inexpensive
	- Easy to install and maintain
- Limited bandwidth availability
	- Physics limits electrical signals through copper
- Wide area networks
	- Cable modem, DSL, T1/T3 local loop
- Often combined with fiber
	- Copper on the local loop, fiber in the backbone
### DSL
- ADSL (Asymmetric Digital Subscriber Line)
	- Uses telephone lines
- Download speed is faster than the upload speed (asymmetric)
	- ~ 10,000 foot limitation from the central office (CO)
	- 200 Mbit/s downstream / 20 Mbit/s upstream are common
	- Faster speeds may be possible if closer to the CO
- Features:
	- Copper cabling
	- Telephone lines
	- Last mile solutions
- Telephone lines
- Twisted-pair copper cabling
- Dedicated bandwidth
### Cable broadband
- Broadband
	- Transmission across multiple frequencies
	- Different traffic types
- Data on the "cable" network
	- DOCSIS (Data Over Cable Service Interface Specification)
- High-speed networking
	- 50 Mbit/s through 1000 Mbit/s are common
- Multiple services
	- data, voice, video
- Cabling that carrier TV signals
- Coaxial cabling
- Shared bandwidth
### Fiber
- High speed data communication
	- Frequencies of light
- Higher installation cost than copper
	- Equipment is more costly and more difficult to repair
	- communication over long distance
- Larger installation in the WAN core
	- Supports very high data rates
	- SONET, wavelength division multiplexing
- Fiber is slowly approaching the premises
	- Business and home use
### Leased Line
- Exclusive connection for a customer over copper or fiber cables
- Described by:
	- Dedicated, point-to-point, always-on connections
	- Typically used by businesses and organizations
	- WAN links
### Metro Ethernet
- Metro-E
	- Metropolitan-area network
	- A contained regional area
- Connect your sites with Ethernet
- The provider network is optional
	- Local fiber network
	- Wavelength-division multiplexing
	- High speed, multiple wavelengths of light
- Metro optical
	- optical connectivity that can span hundreds of kilometers
