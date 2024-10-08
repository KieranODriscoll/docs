# 1.2e - Zero Trust
## Zero Trust
- Many networks are relatively open on the inside
	- Once you're through the firewall, there are few security controls\
- Zero trust is a holistic approach to network security
	- Covers every device, every process, every person
- Everything must be verified
	- Nothing is inherently trusted
	- Multi-factor authentication, encryption, system permissions, additional firewalls, monitoring and analytics, etc
### Planes of Operation
- Split the network into functional planes
	- Applies to both physical, virtual and cloud components
- Data Plane
	- Process the frames, packets and network data
	- Processing, forwarding, trunking, encrypting, NAT
	- Responsible for the movement of packets within a network
	- Subjects are the entities that initiate data communications
- Control
	- Manages the actions of the data plane
	- Define policies and rules
	- Determines how packets should be forwarded
	- Routing tables, session tables, NAT tables
	- Responsible for deciding on access based on policies and threats, which is a dynamic and multifaceted task
	- Considers user behavior as part of its decision-making process, employing security decisions based on user behavior is only one aspect of its function
	- Can indirectly limit potential damage zones by enforcing segmented access to network resources, its primary role should not be confused with the outcomes of its policy enforcement
	- Does not ensure the efficient transmission of data - Role of the data plane
	- Policy-driven access control, policy administrator and the policy engine are located in the control plane 
### Controlling Trust
- Adaptive identity
	- Consider the source and the requested resources
	- Multiple risk indicators - relationship to the organization, physical location, type of connecting IP
	- including context in the authentication process. Authentication systems take into account factors such as user's location, device, and behavior before granting access
### Policy Enforcement Point
- Subjects and systems
	- End users, applications, non-human entities
- Policy Enforcement Point (PEP)
	- The gatekeeper
	- Data plane component that enforces the security policies defined at the Control Plane by the Policy Decision Point (PDP)
- Allow, monitor, and terminate connections
	- Can consist of multiple components working together
![](Pasted%20image%2020240905134240.png)
### Applying trust in the planes
- Policy Decision Point
	- There's a process for making an authentication decision
- Policy Engine
	- Evaluates each access decision based on policy and other information sources
	- Grant, deny, revoke
- Policy Administrator
	- Communicates with the Policy Enforcement Point
	- Generate access tokens or credentials
	- Tells the PEP to allow or disallow access address, etc
	- Make the authentication stronger, if needed
- Threat scope reduction
	- Decrease the number of possible entry points
- Policy-driven access control
	- Combine the adaptive identify with a predefined set of rules
### Security Zones
- Security is more than a one-to-one relationship
	- Broad categorizations provide a security-related foundation
- Where are you coming from and where are you going
	- Trusted, untrusted
	- Internal network, external network
	- VPN 1, VPN 5, VPN 11
	- Marketing, IT, Accounting, Human Resources
- Using the zones may be enough by itself to deny access
	- For example, Untrusted to trusted zone traffic
- Some zones are implicitly trusted
	- For example, Trusted to Internal zone traffic
### Zero Trust Across Planes
![](Pasted%20image%2020240905134844.png)
