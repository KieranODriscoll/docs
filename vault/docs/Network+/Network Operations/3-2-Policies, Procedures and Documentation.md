# 3.2 - Policies, Procedures and Documentation
## Plans and Procedures
### Change Management
- How to make a change
	- Upgrade software, change firewall configuration, modify switch p orts
- One of the most common risks in the enterprise
	- Occurs very frequently
- Often overlooked or ignored
	- Did you feel that bite?
- Have clear policies
	- Frequency, duration, installation process, fallback procedures
- Sometimes extremely difficult to implement
	- It's hard to change corporate culture
### Security Incidents
- User clicks an email attachment and executes malware
	- Malware than communicates with external servers
- DDoS
	- botnet attack
- Confidential information is stolen
	- Thief wants money or it goes public
- User installs peer-to-peer software and allows external access to internal servers
### NIST SP800-61
- National Institute of Standards and Technology
	- Computer Security Incident
	- Handling Guide
- The incident response lifecycle:
	- Preparation
	- Detection and Analysis
	- Containment, Eradication, and Recovery
	- Post-incident Activity
### Disaster Recovery Plan
- If a disaster happens, IT should be ready
	- Part of business continuity planning
	- Keep the organization up and running
- Disasters are many and varied
	- Natural disasters
	- Technology or system failures
	- Human-created disasters
- A comprehensive plan
	- Recovery location
	- Data recovery method
	- Application restoration
	- IT team and employee availability
### Continuity of Operations Planning (COOP)
- Not everything goes according to plan
	- Disasters can cause a disruption to the norm
- We rely on computer systems
	- Technology is pervasive
- There needs to be an alternative
	- Manual transactions
	- Paper receipts
	- Phone calls for transaction approval
- There must be documented and tested before problem occurs
### System Life Cycle
- Managing asset disposal
	- Desktops, laptops, tablets, mobile devices
- Disposal becomes a legal issue
	- Some information must not be a destroyed
	- Consider offsite storage
- You don't want critical information in the trash
	- People really do dumpster dive
	- Recycling can be a security concern
### Standard Operating Procedures
- Organizations have different business objectives
	- Processes and procedures
- Operational Procedures
	- Downtime notifications, facilities issues
- Software upgrades - testing, change control
- Documentation is the key
	- Everyone can review and understand the policies
### Common agreements
- Service Level Agreements  (SLA)
	- Minimum terms for services provided
	- Uptime, response time agreement, etc
	- Commonly used between customers and service providers
- Memorandum of Understanding (MOU)
	- Both sides agree on the contents of the memorandum
	- Usually includes statements of confidentiality
	- Informal letter of intent; not a signed contract
### Non-disclosure agreement (NDA)
- Confidentiality agreement between parties
	- Information in the agreement should not be disclosed
- Protects confidential information
	- Trade secrets, business activities
	- Anything else listed in the NDA
- Unilateral or Bilateral (or multilateral)
	- One-way NDA or mutual NDA
- Formal contract - Signatures are usually required
## Security Policies
### Password Policy
- Make your password strong
	- Resist guessing or brute-force attack
- Increase password entropy
	- No single words, no obvious passwords
	- Mix upper and lower case and use special characters
- Strong passwords are at least 8 characters
- Prevent password reuse
	- System remembers password history, requires unique passwords
### Acceptable Use Policies (AUP)
- What is acceptable use of company assets
	- Detailed documentation
	- May be documented in the Rules of Behaviour
- Covers many tropics
	- Internet use, telephones, computers, mobile devices, etc
- Used by an organization to limit legal liability
	- If someone is dismissed, these are the well-documented reasons why
### BYOD
- Bring your Own Device or Bring your Own Technology
- Employee owns the device
	- Needs to meet the company's requirements
- Difficult to secure
	- It's both a home device and a work device
	- How is data protected?
	- What happens to the data when a device is sold or traded in?
### Remote access policies
- Easy to control internal communication
	- More difficult when people leave the building
- Policy for everyone
	- Including third-party access
- Specific technical requirements
	- Encrypted connection, confidential credentials, use of network, hardware and software requirements
### Onboarding
- Bring a new person into the organization
	- New hires or transfers
- IT agreements need to be signed
	- May be part of the employee handbook or a separate AUP
- Create accounts
	- Associate the user with the proper groups and departments
- Provide required IT hardware
	- Laptops, tablets, etc
	- Preconfigured and ready to go
### Off-boarding
- This process should be pre-planned
	- You don't want to decide how to do things at this point
- What happens to the hardware?
- What happens to the data?
- Account information is usually deactivated
	- But not always deleted
### Data Loss Prevention (DLP)
- Where's your data?
	- Social Security Numbers, credit card numbers, medical records
	- Detailed policies needed to define what is allowed
		- How is sensitive data transferred
		- Is the data encrypted? How?
	- DLP solutions can watch and alert on policy violations
		- Often requires multiple solutions in different places
- DLP systems are used to ensure that end-users do not send sensitive or critical information outside the corporate network
- Help a network admin control what data end users can transfer
### Security Policy
- Documentation of the organization's processes and procedures regarding IT security
	- Every organization has a different focus
- Almost everything in this module would be included
	- Remote access, building security, incident response, etc
- This is not a static document
	- Change is constant

## Network Documentation
### Floor Plans
- Overlay the wired and wireless network with the existing architectural layout
	- Wires in the ceiling
	- Access point locations
- Can be useful for patch panel labels
	- Associated a desk with a number
- Used for planning
	- Avoid heavy machinery
	- Identify closet locations
### Physical network maps
- Follows the physical wire and device
	- Can include physical rack locations
### Distribution frames
- Passive cable termination
	- Punch down blocks
	- Patch panels
- Usually mounted on the wall or flat surface
	- Uses a bit of real-estate
- All transport media
	- Copper, fiber, voice, and data
- Often used as a room or location
	- It's a significant part of the network
### Main Distribution Frame (MDF)
- Central point of the network
	- Usually in a data center
- Termination points for WAN links
	- Connects the inside to the outside
- Good test point
	- Test in both directions
- This is often the data center
	- The central point for data
### Intermediate Distribution Frame (IDF)
- Extension of the MDF
	- A strategic distribution point
- Connects the users to the network
	- Uplinks from the MDF
	- Workgroup switches
	- Other local resources
- Common in medium to large organizations
	- Users are geographically diverse
### Logical network maps
- Specialized software
	- Vision, OmniGraffle, Gliffy.com
- High Level views
	- WAN layout, application flows
- Useful for planning and collaboration
### Managing your cables
- ANSI/TIA/EIA 606
	- Administrative Standard for the Telecommunications
	- Infrastructure of Commercial Buildings
- Presentation of information
	- Reports, drawings, work orders
- Pathway, space, grounding
	- Identifiers, Labeling
- Cables
	- Identifiers, labels, color coding, bar coding
### Labeling
- Everything is tagged and labeled
	- A standard format
- Port labeling
	- CB01-01A-D088
	- CB01 - Main facility
	- 01A - Floor 1, space A
	- D088 - Data port 88
- All cables are documented
	- Central database
### Site surveys
- Determine existing wireless landscape
	- Sample the existing wireless spectrum
- Identify existing access points
- Work around existing frequencies
	- Layout and plan for interference
- Plan for ongoing site surveys
	- Things will certainly change
- Heat maps
	- Identify wireless signal strengths
	- Helps with deciding multiple APs location to ensure the best wireless signal coverage for a network
### Audit and Assessment Report
- Validate existing security policies
	- Are we following our own rules?
- Internal audits
	- Self-imposed checks
	- Validate permissions, check access logs, verify user accounts status
- External audits
	- Third-party performs the checks
	- May be required for compliance regulations
### Baselines
- Broadly defined
	- What does it mean to you?
	- Application response time, network throughput, etc
- Point of reference
	- Accumulate knowledge
	- Examine the past to predict the future
	- Useful for planning
## High Availability
### Fault Tolerance
- Maintain uptime in case of a failure
	- If a problem occurs, what happens?
	- Can degrade performance
- Fault tolerance adds complexity
	- The cost of managing the environment increases
- Single device fault tolerance
	- RAID, redundant power supplies, redundant NICs
- Multiple device fault tolerance
	- Server farms with load balancing
	- Multiple network paths
### Redundancy and Fault Tolerance
- Redundant hardware components
	- Multiple devices, load balancing power supplies
- RAID
	- Redundant Array of Independent Disks
- Uninterruptible power supplies (UPS)
	- Prepare for the disconnections
- Clustering
	- A logical collection of servers
- Load balancing
	- Shared service load across components
### High availability
- Redundancy doesn't always mean always available
	- May need to be enabled manually
- HA (High Availability)
	- Always on, always available
- May include many different components working together
- Higher availability almost always means higher costs
	- There's always another contingency you could add
	- Upgraded power, high quality server components, etc
### Load balancing
- Some servers are active, others are on standby
	- If an active server fails, the passive server takes its place
- ![](Pasted%20image%2020240611145005.png)
### NIC Teaming
- Load balancing / Fail Over (LBFO)
	- Aggregate bandwidth, redundant paths
	- Becomes more important in the virtual world
- Multiple network adapters
	- Looks like a single adapter
	- Integrate with switches
- NICs talk to each other
	- Usually multicast instead of broadcast
	- Fails over when a NIC doesn't respond