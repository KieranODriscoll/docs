# 3.1b - Infrastructure Concepts
## Network Infrastructure Concepts
### Physical isolation
- Devices are physically separate
	- Air gap between Switch A and Switch B
- Must be connected to provide communication
	- Direct connect, or another switch or router
- Web servers in one rack
	- Database servers on another
- Customer A on one switch, customer B on another
	- No opportunity for mixing data
### Physical segmentation
- Separate devices
	- Multiple units, separate infrastructure
### Logical segmentation with VLANs
- Virtual Local Area Networks (VLANs)
	- Separate logically instead of physically
	- Cannot communicate between VLANs without a Layer 3 device / router
### SDN (Software Defined Networking)
- Networking devices have different functional planes of operation
	- Data, control, and management planes
- Split the functions into separate logical units
	- Extend the functionality and management of a single device
	- Perfectly built for the cloud
- Infrastructure Layer / Data Plane
	- Process the network frames and packets
	- Forwarding, trunking, encrypting, NAT
- Control Layer/ Control Plane
	- Manages the actions of the data plane
	- Routing tables, session tables, NAT tables
	- Dynamic routing protocol updates
- Application layer / Management plane
	- Configure and manage the device
	- SSH, browser, API
## Other Infrastructure Concepts
### Attacks can happen anywhere
- Two categories for IT security
	- The on-premises data is more secure
	- The cloud-based data is more secure
- Cloud-based security is centralized and costs less
	- No dedicated hardware, no data center to secure
	- A third-party handles everything
- On-premises puts the security burden on the client
	- Data center security and infrastructure costs
- Attackers want your data - they don't care where it is
### On-premises security
- Customize your security posture
	- Full control when everything is in-house
- On-site IT team can manage security better
	- The local team can ensure everything is secure
	- A local team can be expensive and difficult to staff
- Local team maintains uptime and availability
	- System checks can occur at any time
	- No phone call for support
- Security changes can take time
	- New equipment, configurations, and additional costs
### Centralized vs decentralized
- Most organizations are physically decentralized 
	- Many locations, cloud providers, operating systems, etc
- Difficult to manage and protect so many diverse systems
	- Centralized the security management
- A centralized approach
	- Correlated alerts
	- Consolidated log file analysis
	- Comprehensive system status and maintenance/patching
	- Single point of failure, potential performance issues
### Virtualization
- Run many different operating systems on the same hardware
- Each application instance has its own operating system
	- Adds overhead and complexity
	- Virtualization is relatively expensive
- ![[Pasted image 20240913135753.png]]
### Application containerization
- Container
	- Contains everything you need to run an application
	- Code and dependencies
	- A standardized unit of software
- An isolated process in a sandbox
	- Self-contained
	- Apps can't interact with each other
- Container image
	- A standard for portability
	- Lightweight, uses the host kernel
	- Secure separation between applications
- ![[Pasted image 20240913135759.png]]
### IoT (Internet of Things)
- Sensors
	- Heating and cooling, lighting
- Smart devices
	- Home automation, video doorbells
- Wearable technology
	- Watches, health monitors
- Facility automation
	- Temperature, air quality, lighting
- Weak defaults
	- IOT manufacturers are not security professionals
### SCADA / ICS
- Supervisory Control and Data Acquisition System
	- Large-scale, multi-site Industrial Control Systems (ICS)
- PC manages equipment
	- Power generation, refining, manufacturing equipment
	- Facilities, industrial, energy, logistics
- Distributed control systems
	- No access from the outside
### RTOS (Real-time Operating System)
- An operating system with a deterministic processing schedule
	- No time to wait for other processes
	- Industrial equipment, automobiles
	- Military environments
- Extremely sensitive to security issues
	- Non-trivial systems
	- Need to always be available
	- Difficult to know what type of security is in place
### Embedded systems
- Hardware and software designed for a specific function
	- Or to operate as part of a larger system
- Is built with only this task in mind
	- Can be optimized for size and/or cost
- Common examples
	- Traffic light controllers
	- Digital watches
	- Medical imaging systems
### High availability
- Redundancy doesn't always mean always available
	- May need to be powered on manually
- HA (High availability)
	- Always on, always available
- May include many different components working together
	- Active/Active can provider scalability advantages
- High availability almost always means higher costs
	- There's always another contingency you could add
	- Upgraded power, high-quality server components, etc