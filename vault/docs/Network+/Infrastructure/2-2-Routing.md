# 2.2 - Routing
## Dynamic Routing
### Dynamic Routing Protocols
- Listen for subnet information from other routers
	- Sent from router to router
- Provide subnet information to other routers
	- Tell others what you know
- Determine the best path based on the gathered information
	- Every routing protocol has its own way of doing this
- When network changes occur, update the available routes
	- Different convergence process for every dynamic routing protocol
### Which routing protocol to use
- What exactly is a route?
	- It is based on the state of the link?
	- It is based on how far away it is?
- How does the protocol determine the best path
	- Some formula is applied to the criteria to create a metric
	- Rank the routes from best to worst
- Recover after a change to the network
	- Convergence time can vary widely between routing protocols
- Standard or proprietary protocol?
	- OSPF and RIP are standards, some functions of EIGRP are Cisco proprietary 
### Distance-vector routing protocols
- Information passed between routers contains network details
	- How many "hops" away is another network
	- The deciding "vector" is the "distance"?
- Usually automatic
	- Very little configuration
- Good for smaller networks
	- Doesn't scale well to very large networks
- Does not require the router to know the complete network path, only knows its direct neighbors
- Shares routing table with neighbors and sends periodic updates
- RIP (Routing Information Protocol)
	- Was used for dynamic routing in smaller networks
	- Sends the complete routing table to the next router every 30 seconds
	- Has a maximum hop count of 15
	- 3 Versions
		- RIPv1 - Uses broadcast, works with classful routing
		- RIPv2 - Uses multicast, fixed address 224.0.0.9, works with classless routing
		- RIP Next Generation - Works with IPv6, IPv6 multicast address FF02::9
- EIGRP (Enhanced Interior Gateway Routing Protocol)
	- Performs efficient routing information exchange
	- Keeps a copy of the neighbors routing table to find the best route
	- Stores the following information on each participating router:
		- Neighbor table - stores the neighbor's information
		- Topology table - Stores the neighbor's routing information
		- Routing table - stores the best routes to the destination networks
#### Route Poisoning
- Route poisoning is a method to prevent a router from sending packets through a route that has become invalid within computer networks.
- This is achieved by changing the route's metric to a value that exceed the maximum allowable hope count so that the route is advertised as unreachable
### Link-state routing protocols
- Information passed between routers is related to the current connectivity
	- If it's up, you can get there
	- If it's down, you can't
- Consider the speed of the link
	- Faster is always better, right?
- Very scalable
	- Used most often in large networks
- OSPF (Open Shortest Path First)
	- Large, scalable routing protocol
	- Uses the shortest-path algorithm to find the shortest path to the destination
	- Calculates the path based on the cost of the route
	- Determines the network design by publishing its list of neighbors
		- Routers share a list of neighbors with the other routers
		- This information is used to determine the shortest path
	- Each router using ISPF keeps a link state database, each has the same information but independent in calculating the cost of a route
	- Backbone of the OSPF network is known as Area 0. Each area you create must be connected to Area 0.
	- ![](Pasted%20image%2020240627140949.png)
### Hybrid routing protocols
- A little link-state, a little distance-vector
	- Not many examples of hybrid routing protocols
- Is a combination of distance vector and link-state protocols
- Uses TCP for communication between the routers on the internet
	- An ASN (or Autonomous System Number) is used to control routing with BGP routing protocols to route traffic across the network. An Autonomous System (AS) is a group of one or more IP prefixes (lists of IP addresses accessible on a network) run by one or more network operators that maintain a single, clearly defined routing policy. Network operators need Autonomous System Numbers (ASNs) to control routing within their networks and to exchange routing information with other Internet Service Providers (ISPs). There are 2-byte and 4-byte ASN variants in use on the internet.
- Provides support for Autonomous System Numbers (ASNs)
- Uses routing table to:
	- Know the list of routers and their reachable destinations
	- Their cost metrics for each path
- BGP (Border Gateway Protocol)
	- Determines route based on paths, network policies or configured rule-sets
	- Is an inter-autonomous domain communication protocol
	- Is an application-layer protocol that works on TCP port 179
	- Uses the following for communication
		- Internal BGP (iBGP): Within a single autonomous domain, communication is restricted only within the single autonomous domain, works like OSPF protocol
		- External BGP: Between multiple autonomous domains, several autonomous domains communicate with each other using eBGP
	- Advertises its routes and learns the routes form other routers to choose the best route to reach the destination
	- Can work with:
		- Single-homed - uses a single ISP connection, it advertises its routes with the ISP and learns its default route
		- Dual-homed sites - Instead of one single connection, there are two connections from the single ISP. These connections can be configured on a single router or two routers, mainly used for load balancing
		- Multi-homing - There are more than two connections from either a single ISP or more than one ISP. When there is more than one ISP, it is due to fault tolerance so that if one ISP fails, the other ISP continues to function. It is also to use the best route provided by any of the ISPs
		- Dual multi-homing - There are two connections from several ISPs. This is implemented when you need to have a high level of redundancy
	- ![](Pasted%20image%2020240627142447.png)
	- will route data through another WAN link if redundant WAN links are available
## Routing Technologies
### Routing Tables
- A list of directions for your packets
	- A table with many routes to your destination
	- Packets stop at every router and ask for directions
- Routing tables in routers, workstations and other devices
	- Every device needs directions
### The hop
- A hop is a packet passing through a router
- The next home is the destination address of the next gateway
- A router doesn't need to know how to get everywhere
	- It just needs to know how to get out of here
	- A default routes handles everything no specifically listed
- "Time to live" in IPv4, "hop limit" in IPv6
	- Avoids a packet looping forever
### Configuring the next hop
- Every router needs to know where traffic should be sent
	- Your packet is always asking for directions
- A router with the incorrect next hop will result in a routing problem
	- Data will go the wrong direction
	- A routing loop is easy to create
	- You'll know quickly if there's a loop
### Default routes
- A route when no other route matches
	- "The gateway of last resort"
- A remote site may have only one route
	- Go that way -> rest of the world
	- Destination of 0.0.0.0/0
- Can dramatically simplify the routing process
	- Works in conjunction with all other routing methods
### Routing metrics
- Each routing protocol has its own way of calculating the best route
	- RIPv2, OSPF, EIGRP
- Metric values are assigned by the routing protocol
	- RIPv2 metrics aren't useful to OSPF or EIGRP
- Use metrics to choose between redundant links
	- Choose the lowest metric
	- 1 is better than 2
### Administrative distances
 - What if you have two routing protocols, both know about a route to a subnet?
	- Two routing protocols, two completely different metric calculations
	- You can't compare metrics across routing protocols
	- Which one do you choose
- Administrative distances
	- Used by the router to determine which routing protocol has priority
	- Most preferred is low AD value
	- Least preferred is high AD value
### Exterior vs Interior
#### Interior Routing
- Takes place within a single network known as an autonomous system
- Can use one or more protocols for routing
- Examples:
	- RIP
	- OSPF
	- EIGRP
#### Exterior Routing
- Takes place between autonomous systems
- Can use only one routing protocol
- Example:
	- BGP
- ![](Pasted%20image%2020240627143147.png)
### Managing network utilization
- Many different devices
- Many different applications
- Different apps have different network requirements
	- Voice is real-time
	- Recorded streaming has a buffer
	- Database application is interactive
- Some applications are more important than others
	- Voice traffic needs priority over youtube
### Traffic Shaping
- traffic shaping and packet shaping
- Control by bandwidth usage or data rates
- Set important applications to have high priorities than other apps
- Manage the Quality of Service (QoS)
	- Routers, switches, firewalls, QoS devices
	- QoS operates at either Layer 2 or Layer 3 of the OSI model
