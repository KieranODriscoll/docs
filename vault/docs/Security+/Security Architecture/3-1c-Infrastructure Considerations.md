# 3.1c - Infrastructure Considerations
## Availability
- System uptime
	- Access data, complete transactions
	- A foundation of IT security
- A balancing act with security
	- Available, but only to the right people
- We spend a lot of time and money on availability
	- Monitoring, redundant systems
- An important metric
	- We are often evaluated on total available time
## Resilience
- Eventually, something will happen
	- Can you maintain availability
	- Can you recover? How quickly?
- Based on many different variables
	- The root cause
	- Replacement hardware installation
	- Software patch availability
	- Redundant systems
- Commonly referenced as MTTR
	- Mean Time to Repair
## Cost
- How much money is required?
	- Everything ultimately comes down to cost
	- Initial installation
	- Very different across platforms
- Ongoing maintenance
	- Annual ongoing cost
- Replacement or repair costs
	- You might need more than one
- Tax implications
	- Operating or capital expense
- Total Cost of Ownership
	- Includes initial purchase price of the tool buy also the ongoing expenses related to maintenance, updates and other associated costs over its lifecycle
## Responsiveness
- Request information
	- Get a response
	- How quickly did that happen
- Especially important for interactive applications
	- Humans are sensitive to delays
- Speed is an important metric
	- All parts of the application contribute
	- There's always a weakest link
## Scalability
- How quickly and easily can we increase or decrease capacity
	- This might happen many times a day
	- Elasticity
- There's always a resource challenge
	- What's preventing scalability?
- Needs to include security monitoring
	- Increases and decreases as the system scales
## Easy of deployment
- An application has moving parts
	- Web server, database, caching server, firewall, etc
- This might be very simple
	- Orchestration / automation
- Important to consider during the product engineering phase
	- One missed detail can cause deployment issues
## Risk transference
- Many methods to minimize risk
	- Transfer the risk to a third-party
- Cybersecurity insurance
	- Attacks and downtime can be covered
	- Popular with the rise in ransomware
- Recover internal losses
	- Outages and business downtime
- Protect against legal issues from customers
	- Limit the costs associated with legal proceedings
## Ease of recovery
- Something will eventually go wrong
	- Time is money
	- How easily can you recover?
- Malware infection
	- Reload operating system from original media - 1 hour
	- Reload from corporate image - 10 minutes
- Another important design criteria
	- This may be critical to the final product
## Patch availability
- Software isn't usually static
	- Bug fixes, security updates, etc
- This is often the first task after installation
	- Make sure you're running the latest version
- Most companies have regular updates
	- Microsoft's monthly patch schedule
- Some companies rarely patch
	- This might be a significant concern
## Inability to patch
- What if patching wasn't an option?
	- This happens more often than you think
- Embedded systems
	- HVAC controls
	- Time clocks
- Not designed for end-user updates
	- This is a bit short sighted
	- Especially these days
- May need additional security controls
	- A firewall for your time clock
## Power
- A foundational element
	- This can require extensive engineering
- Overall power requirements
	- Data center vs office building
- Primary power
	- One or more providers
- Backup services
	- UPS (Uninterruptible Power Supply)
	- Generators
## Compute
- An application's heavy lifting
	- More than just a single CPU
- The compute engine
	- More options available in the cloud
- May be limited to a single process
	- Easier to develop
- Use multiple CPUs across multiple clouds
	- Additional complexity
	- Enhanced scalability