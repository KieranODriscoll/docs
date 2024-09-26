# Definitions
## Frequency
- Is the number of occurrences of a repeating event per unit of time.
- WIFI networks utilize 3 different frequency bands: 2.4GHz, 5GHz and 6GHz
## Modulation
- Process of varying in one or more properties of a periodic waveform, called the carrier signal, with a separate signal called the modulation signal that typically contains information to be transmitted
- WIFI uses different digital modulation schemes for data transmission such as Orthogonal frequency-division multiplexing (OFDM), Quadrature Amplitude Modulation (OAM) and Quadrature Phase-shift keying (PSK)
## Site Survey Report
- Process of planning and designing a wireless network to provide a wireless solution that will deliver the required wireless coverage, data rates, network capacity, roaming capability, and quality of service (QoS).
- Contains a floorplan of the areas surveyed with the wireless coverage areas and signal strengths notated on it.
## Logical Network Diagram
- Illustrates the flow of data across a network and is used to show how devices communicate with each other
- Usually includes the subnets, network objects and devices, routing protocols and domains, voice gateways, traffic flow and network segments in a given network
## Physical Network Diagram
- provides an overview of the physical components of a network, including devices, cables and their interconnections.
- Typically includes information about the location of network devices, such as routers, switches, and servers
## Wiring Diagram
- Includes a floorplan or rack diagram so you can see how the cables are run in the physical environment
- Are used to clearly label which cables are connected to which ports.
- More in-depth wiring diagram will include a floorplan or rack diagram, so you can see how the cables are run in the physical environment
## VLAN Access Ports
- is a connection on a switch that transmits data to and from a specific VLAN
- Access port is only assigned to a single VLAN, it sends and receives frames that aren't tagged and only have the access VLAN value
- Does not cause signal issues because the frames remain within the same VLAN.
- If it does happen to receive a tagged packet, it will simply avoid it
- Simpler configuration but not the most efficient choice if the network is even moderately
## VLAN Trunk Ports
- Unlike an access port, a trunk port can transmit data from multiple VLANs
- If a dozen VLAN are on a particular switch, you don't need additional cables or switches for each VLAN - just that single link
- A trunk port allows you to send all those signals for each switch or router across a single trunk link
- A trunk port must use tagging in order to allow signals to get to the correct endpoint
- Typically offer higher bandwidth and lower latency than access ports
## Broadcast Domain
- A logical division of a computer network in which all nodes can reach each other by broadcast at the data link layer
- A broadcast domain can be within the same LAN segment, or it can be bridged to other LAN segments
- Routers break up broadcast domains.
- Example:
	- A small law office has a network with three switches (8 ports), one hub (4 ports), and one router (2 ports). Switch 1 (switch port 8) is connected to an interface port (FastEthernet0/0) on the router. Switch 2 (switch port 8) and switch 3 (switch port 8) are connected to Switch 1 (switch ports 1 and 2). The hub has three computers plugged into it on ports 1, 2, and 3. The fourth port on the hub is connected to the router's other interface port (FastEthernet0/1). Based on the configuration described here, how many broadcast domains are there within this network?
		- Router breaks up broadcast domain, therefore there are two broadcast domains in this network - one for each side of the router.
## Collision Domain
- Is a network segment connected by a shared medium or through repeaters where simultaneous data transmissions collide with one another
- Hubs do not break up collision domains, but routers and switches do
- For each switchport or interface on a switch or router, there is a new collision domain
- Example:
	- A small law office has a network with three switches (8 ports), one hub (4 ports), and one router (2 ports). Switch 1 (switch port 8) is connected to an interface port (FastEthernet0/0) on the router. Switch 2 (switch port 8) and switch 3 (switch port 8) are connected to Switch 1 (switch ports 1 and 2). The hub has three computers plugged into it on ports 1, 2, and 3. The fourth port on the hub is connected to the router's other interface port (FastEthernet0/1). Based on the configuration described here, how many collision domains are there within this network?
		- Therefore, in this network, you will have one collision domain for the hub and its clients that are connected to FastEthernet0/1. There is a second collision domain for the router’s other interface (FastEthernet0/0) that is shared with Switch 1 (switch port 8). There is a third collision domain for the connection between Switch 2 and Switch 1, and a fourth domain for the connection between Switch 3 and Switch 1. If there were additional clients on any of these switches, each client would also be a part of its own collision domain, but since none were mentioned, we only have 4 collision domains in this network
	- You are installing a Small Office/Home Office (SOHO) network consisting of a router with 2 ports, a switch with 8 ports, and a hub with 4 ports. The router has one port connected to a cable modem and one port connected to switch port #1. The other 6 ports on the switch each have a desktop computer connected to them. The hub's first port is connected to switch port #2. Based on the description provided, how many collision domains exist in this network?
		- Based on the description provided, there are 9 collision domains. Each port on the router is a collision domain (2), each port on the switch is a collision domain (8), and all of the ports on the hub make up a single collision domain (1). But, since one of the ports on the router is connected to one of the switch ports, they are in the same collision domain (-1). Similarly, the hub and the switch share a common collision domain connected over the switch port (-1). This gives us 9 collision domains total: the 8 ports on the switch and the 1 port on the route that is used by the cable modem.
## Online Certification Status Protocol
- internet protocol that checks the validity status of a certification in real time. Fastest approach
- An alternative is CRL or Certification Revocation Lists
## SPOF
- Single Point of Failure
## CAM
- Content-addressable memory
- Used in certain very-high-speed searching applications
- An example would be lookup tables on networking devices
