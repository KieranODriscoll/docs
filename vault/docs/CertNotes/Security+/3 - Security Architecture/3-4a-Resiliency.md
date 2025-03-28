# 3.4a - Resiliency
## High availability
- Redundancy doesn't always mean always available
	- May need to be powered on manually
- HA (High availability)
	- Always on, always available
- May include many different components working together
	- Active/Active can provide scalability advantages
- Higher availability almost always means higher costs
	- There's always another contingency you could add
	- Upgraded power, high-quality server components, etc
## Server clustering
- Combine two or more servers
	- Appears and operates as a single large server
	- Users only see one device
- Easily increase capacity and availability
	- Add more servers to the cluster
- Usually configured in the operating system
	- All devices in the cluster commonly use the same OS
## Load balancing
- Load is distributed across multiple servers
	- The servers are often unaware of each other
- Distribute the load across multiple devices
	- Can be different operating systems
- The load balancer adds or removes devices
	- Add a server to increase capacity
	- Remove any servers not responding
## Site resiliency
- Recovery site is prepped
	- Data is synchronized
- A disaster is called
	- Business processes failover to the alternate processing site
- Problem is addressed
	- This can take hours, weeks, or longer
- Revert back to the primary location
	- The process must be documented for both directions
## Hot site
- An exact replica
	- Duplicate everything
- Stocked with hardware
	- Constantly updated
	- You buy two of everything
- Applications and software are constantly updated
	- Automated replication
- Flip a switch and everything moves
	- This may be quite a few switches
## Cold site
- No hardware
	- Empty building
- No data
	- Bring it with you
- No people
	- Bus in your team
## Warm site
- Somewhere between cold and hot
	- Just enough to get going
- Big room with rack space
	- You bring the hardware
- Hardware is ready and waiting
	- You bring the software and data
	- Geographic dispersion
- These sites should be physically different than the organization's primary location
	- Many disruptions can affect a large area
- Can be a logistical challenge
	- Transporting equipment
	- Getting employee's on-site
	- Getting back to the main office
## Platform diversity
- Every operating system contains potential security issues
	- You can't avoid them
- Many security vulnerabilities are specific to a single OS
	- Windows vulnerabilities don't commonly affect Linux or macOS
	- and vice versa
- Use many different platforms
	- Different applications, clients, and OSes
	- Spread the risk around
## Multi-cloud systems
- Plan for cloud outages
	- These can sometimes happen
- Data is both geographically dispersed and cloud service dispersed
	- A breach with one provider would not affect the others
	- Plan for every contingency
## Continuity of operations planning (COOP)
- Not everything goes according to plan
	- Disasters can cause a disruption to the norm
- We rely on our computer systems
	- Technology is pervasive
- There needs to be an alternative
	- Manual transactions
	- Paper receipts
	- Phone calls for transaction approvals
- These must be documented and tested before a problem occurs