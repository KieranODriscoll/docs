# 2.1 - Networking Devices
## Networking Devices
### Hub
- Mutli-port repeater
	- Traffic goin in one port is repeated to every other port
	- OSI Layer 1
- Everything is half-duplex
- Becomes less efficient as network speeds increase
- 10 megabit / 100 megabit
- Difficult to find today
- Operates at the physical layer (Layer 1) of the OSI model
- All devices connected by a hub are in a single collision domain and a single broadcast domain, therefore they must use a half-duplex for communication and CSMA/CD
### Bridge
- Imagine a switch with two to four ports
	- Makes forwarding decisions in software
- Connects different physical networks
	- Can connect different topologies
	- Gets around physical network size limitations / collisions
- OSI Layer 2 device
	- Distributes traffic based on MAC address
- Most bridges these days are wireless access points
	- Bridges wired Ethernet to wireless
- Forwards traffic between network segments at the data link layer (Layer 2) of the OSI model using MAC addresses.
- Each switchport on a bridge is a separate collision domain, but all switch ports are in a common broadcast domain
### Switch
- Bridging done in hardware
	- Application-specific integrated circuit (ASIC)
- An OSI layer 2 device
	- Forwards traffic based on data link address
- Many ports and features
	- The core of an enterprise network
	- May provide Power over Ethernet (PoE)
- Multilayer switch
	- Includes Layer 3 (routing) functionality
- A switch connects devices on a computer network by using packet switching to receive and forward data to the destination device Operates at Layer 2 of the OSI and makes switching decisions based upon MAC addresses.
- Each switchport on a switch is a separate collision domain, but all switchports are in a common broadcast domain
- Features
	- Makes forwarding decisions in software
	- Typically capable of connecting fewer network segments than a switch
	- Older and less effective type of network device in comparison to a network switch 
### Router
- Routes traffic between IP subnets
	- OSI layer 3 device
	- Routers inside of switches sometimes called "layer 3 switches"
	- Layer 2 = Switch
	- Layer 3 = Router
- Often connects diverse network types
	- LAN, WAN, copper, fiber
- Rollover cable is used to connect a computer terminal to a router's console port
- Connects computer networks and forwards data between those networks. Operates at network layer 3 of the OSI model and makes routing decisions based upon IP addresses
- Each switchport on a router is a separate collision domain and a separate broadcasting domain
### Access Point
- Not a wireless router
	- A wireless router is a router and an access point in a single device
- An access point is a bridge
	- Extends the wired network onto the wireless network
	- OSI layer 2 device
### Cable Modem
- Broadband
	- Transmission across multiple frequencies
	- Different traffic types
- Data on the "cable" network
	- DOCSIS (Data Over Cable Service Interface Specification)
- High-speed networking
	- 4 Mbits/s through 250Mbits/s are common
	- Gigabit speeds are possible
- Multiple services - Data, voice, video
### DSL modem
- ADSL (Asymmetric Digital Subscriber Line)
	- Uses telephone lines
- Download speed is faster than the upload speed (asymmetric)
- ~10,000 foot limitation from the central office (CO)
- 52 Mbit/s downstream / 16 Mbit/s upstream are common
- Faster speeds may be possible if closer to the CO
### Repeater
- Receive signal, regenerate, resend
	- No forwarding decisions to make
- Common use
	- boost copper or fiber connections
	- Convert one network media to another
	- Extend wireless network reach
### Converting media
- OSI Layer 1 - physical layer signal conversion
- Extend a copper wire over a long distance
	- Convert it to fiber and back again
- You have fiber - The switch only has copper part
- Almost always powered - Especially fiber to copper

## Advanced Networking Devices
### Layer 3 capable switch
- A switch (Layer 2) and router (Layer 3) in the same physical device
	- Layer 3 switch
	- Layer 2 router?
- Switching still operates at OSI Layer 2 , routing still operates at OSI Layer 3
	- There's nothing new or special happening here
### Wireless Networks Everywhere
- Wireless networking is pervasive
	- and you probably don't just have a single access point
- Your access point may not even be in the same building
	- One (or more) at every remote site
- Configurations may change at any moment
	- Access policy, security policies, AP configs
- The network should be invisible to your users
	- Seamless network access, regardless of role
### Wireless LAN controllers
- Centralized management of access points
	- A single "pane of glass"
- Deploy new access points
- Performance and security monitoring
- Configure and deploy changes to all sites
- Report on access point use
- Usually a proprietary system
	- Wireless controller is paired with the access points
### Balancing the load
- Distribute the load
	- Multiple servers, invisible to the end-user
- Large-scale implementations
	- Web server farms, database farms
- Fault tolerance
	- Server outages have no effect, very fast convergence
### Load balancer
- Configurable load - Manage across servers
- TCP offload - Protocol overhead
- SSL offload - Encryption/Decryption
- Caching - Fast response
- Prioritization - QoS
- Content switching - Application-centric balancing
### IDS and IPS
- Intrusion Detection System / Intrusion Prevention System
- Intrusions
	- Exploits against operating systems, applications, etc
	- Buffer overflows, cross-site scripting, other vulnerabilities
- Detection vs Prevention
	- Detection - Alarm or Alert
	- Prevention - Stop it before it gets into the network
### Proxies
- Sits between the users and the external network
- Receives the user requests and send the request on their behalf (the proxy)
- Useful for caching information, access control, URL filtering, content scanning
- Applications may need to know how to use the proxy (explicit)
- Some proxies are invisible (transparent)
### Application Proxies
- Most proxies in use are application proxies
	- The proxy understands the way the application works
- A proxy may only know one application (ie. HTTP)
- Many proxies are multipurpose proxies
	- HTTP, HTTPS, FTP, etc
### VPN Concentrator
- Virtual Private NEtwork
	- Encrypted (private) data traversing a public network
- Concentrator
	- Encryption/decryption access devices
	- Often integrated into a firewall
- Many deployment options
	- Specialized cryptographic hardware
	- Software-based options available
- Used with client software
	- Sometimes built into the OS
### VoIP technologies
- PBX (Private Branch Exchange)
	- The "phone switch"
	- Connects to phone provider network
	- Analog telephone lines to each desk
- VoIP PBX
	- Integrate VoIP devices with a corporate phone switch
- VoIP Gateway
	- Converts between VoIP protocols and traditional PSTN protocols
	- Often built-in to the VoIP PBX
### Network-based Firewalls
- Filter traffic by port numbers or application
- Encrypted traffic - VPN between sites
- Most firewalls can be layer 3 devices (routers)
	- Often sits on the ingress/egress of the network
	- Network Address Translation (NAT), dynamic routing
### VoIP Phone
- A Voice over Internet Protocol
	- Instead of analog phone line or the Plain Old Telephone Service (POTS)
- A relatively complex embedded system
	- Can be an important resource
- Each devices is a computer
	- Separate boot process and network connection
	- Individual configurations
	- Different capabilities and functionalities
### Printer
- Connectivity
	- Ethernet
	- 802.11 Wireless
	- USB
	- Bluetooth / Infrared
### Access control devices
- Card reader
	- Access with a smart card
- Biometric Authentication
	- Fingerprint, retina, voiceprint
- Usually stores a mathematical representation of your biometric
	- Your actual fingerprint isn't saved
- Ethernet connected
	- IP address configured static or DHCP
### Cameras
- CCTV (Closed circuit television)
	- Can replace physical guards
- Camera properties are important
	- Focal length - shorter is wider angle
	- Depth of field - how much is in focus
	- Illumination requirements - See in the dark
- Often many different cameras
	- Networked together and recorded over time
### Surveillance Systems
- Video / Audio surveillance
	- Embedded systems in the cameras and the monitoring stations
- IP addressable
	- Multicast video
	- High definition
### HVAC
- Heating, Ventilation, Air conditioning
- A complex science
	- Not something you can properly design yourself
	- Must be integrated into the fire system
- PC manages equipment
	- Makes cooling and heating decisions for workspaces and data centers
	- Network connectivity is critical
### IoT (Internet of Things) devices
- Appliances - Refrigerators
- Smart devices
	- Smart speakers
- Air control - thermostats, temp control
- Access - Smart doorbells
- May require a segmented network
	- Limit any security breaches
### SCADA / ICS
- Supervisory Control and Data Acquisition System
	- Large-scale, multi-site Industrial Control Systems (ICS)
- PC Manages equipment
	- Power generation, refining, manufacturing equipment
	- Facilities, industrial, energy, logistics
- Distributed control systems
	- Real-time information
	- System control
- Requires extensive segmentation
	- No access from the outside
