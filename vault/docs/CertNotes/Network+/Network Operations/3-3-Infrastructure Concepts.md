# 3.3 - Infrastructure Concepts
## Infrastructure Support
### UPS
- Uninterruptible Power Supply
	- Short-term backup power
	- Blackouts, brownouts, surges
- UPS types
	- standby UPS, line-interactive UPS and on-line UPS
- Features
	- Auto shutdown, battery capacity, outlets, phone line suppression
### Power Distribution Units (PDUs)
- Provide multiple power outlets
	- Usually in a rack
- Often include monitoring and control
	- Manage power capacity
	- Enable or disable individual outlets
### Generators
- Long-term power backup
	- Fuel storage required
- Power an entire building
	- Some power outlets may be marked as generator-powered
- It may take a few minutes to get the generator up to speed
	- Use a battery UPS while the generator is starting
### HVAC
- Heating, Ventilation and Air conditioning
	- Thermodynamics, fluid mechanics and heat transfer
- A complex science
	- Not something you can properly design yourself
	- Must be integrated into the fire system
- PC manages equipment
	- Makes cooling and heating decisions for workspaces and data centers
- A critical component
	- Keeps the equipment and people comfortable
### Fire Suppression
- Data center fire safety
	- Large area, lots of electronics
	- Water isn't the best fire suppression option
- Common to use inert gasses and chemical agents
	- Stored in tanks and dispersed during a fire
	- Many warning signs
- Integrated into HVAC system
	- Monitor for carbon monoxide
	- Enable/disable air handlers
- Pre-action
	- minimizes the risk of accidental release from a wet pipe system.
	- With a pre-action system, both a detector actuation like a smoke detector and a sprinkler must be tripped prior to water being released
- Wet-pipe system
	- Most basic type of fire suppression system, and it involved using a sprinkler system and pipes that always contain water in the pipes.
- Clean agent system
	- use either halocarbon agent or inert gas, when releases the agents will displace the oxygen in the room with the inert gas and suffocates the fire
## Recovery Sites
### Site Resiliency
- Recovery site is prepped
	- Data is synchronized
- A disaster is called
	- Business processes failover to the alternate processing site
- Problem is addressed
	- This can take hours, weeks, longer
- Revert back to the primary location
	- The process must be documented for both directions
### Cold site
- No hardware - empty building
- No data - bring it with you
- No people - bring in the team
### Warm site
- Somewhere between a cold and hot site
	- Just enough to get going
- Bing room with rack space
	- Bring hardware
- Hardware is ready and waiting
	- Bring the software and data
### Hot site
- An exact replica
	- Duplicate everything
- Stocked with hardware
	- Constantly upgrading
	- You buy two of everything
- Applications and software are constantly updated
	- Automated replication
- Flip a switch and everything moves
	- This may be quite a few switches
### Cloud Site
- Use an established cloud provider
	- Can provide enough resources for the recovery process
- No separate facility to manage
	- Online configuration
- Cost can be flat fee or based on use
	- More data, more cost
- The data and applications still need to be moved
	- Large data storage requirements may create a challenge
- Virtual recovery site that allows you to create a recovery version of your organization's enterprise network in the cloud
- Useful when your disaster recovery plan (DRP) includes migrating to a telework or remote operations environment
## Network Redundancy
### Active-passive
- Two devices are installed and configured
	- Only one operates at a time
- If one device fails, other other takes over
	- Constant communication between the pair
- Configuration and real-time session information is constantly synchronized
	- The failover might occur at any time
### Active-Active
- You bought two devices
	- Use both at the same time
- More complex to design and operate
	- Data can flow in many different locations
	- A challenge to manage the flows
	- Monitoring and controlling data requires a very good understanding of the underlying infrastructure
### Diverse Paths
- Create multiple paths
	- More than one internet service provider (ISP)
- May require additional hardware and engineering
	- Advanced dynamic routing protocols
	- Failover processes
	- Local device configuration
- Great for redundancy - no reliance on a single provider
- ![](Pasted%20image%2020240611150546.png)
## High availability Protocols
- FHRP (First Hop Redundancy Protocol)
	- Your computer is configured with a single default gateway
	- We need a way to provide availability if the default gateway fails
- VRRP (Virtual Router Redundancy Protocol)
	- The default router isn't real
	- Devices use a virtual IP for the default gateway
	- If a router disappears, another one takes its place
	- Data continues to flow
	- provides automatic assignment of available Internet Protocol routers to participating hosts
	- Increases the availability and reliability of routing paths via automatic default gateway selections on an IP network
	- Used for internal clients and will not affect the routing of traffic between WANs or autonomous
## Availability Concepts
### Recovery
- Recovery Time Objective (RTO)
	- Get up and running quickly
	- Get back to a particular service level
	- The duration of time and a service level within which a business process must be restored after a disaster to avoid unacceptable consequences associated with a break in continuity
- Recovery Point Objective (RPO)
	- How much data loss is acceptable?
	- Bring the system back online; how far back does data go?
	- Is the interval of time that might pass during a disruption before the quantity of data lost during that period exceeds the BCP's maximum allowable threshold or tolerance
- Mean Time to Repair (MTTR)
	- Time required to fix the issue
	- Average time it takes to repair a network device when it breaks
- Mean Time Between Failures (MTBF)
	- Predict the time between outages
	- Average time between when failures occur on a device.
### Network Device Backup and Restore
- Every device has a configuration
	- IP addresses, security settings, port configurations
	- Most devices allow the configuration to be downloaded and uploaded
	- Configurations may be specific to a version of operating code or firmware
- Revert to previous state
	- Use backups to return to a previous configuration date and time
	- May require a firmware or version downgrade
