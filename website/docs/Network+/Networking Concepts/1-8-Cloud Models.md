# 1.8 - Cloud Models
## Infrastructure as a Service (IaaS)
- Sometimes called Hardware as a Service (HaaS)
	- Outsource your equipment
- You're still responsible for the management
	- and for the security
- Your data is out there, but more within your control
- Web server providers
## Software as a Service (SaaS)
- On-demand software
	- No local installation
	- Why manage your own email distribution? or payroll?
- Central management of data and applications - your data is out there
- A complete application offering
	- No development work require
	- Google mail
## Platform as a Serivce (PaaS)
- No servers, no software, no maintenance team, no HVAC
	- Someone else handles the platform, you handle the development
- You don't have direct control of the data, people, or infrastructure
	- Trained security professionals are watching your stuff
	- Choose carefully
- Put the building blocks together
	- Develop your app from what's available on the platform
	- Salesforce.com

![Pasted_image_20240606152330](//assets/Pasted_image_20240606152330.webp)
## Cloud deployment models
- Private - Your own virtualized local data center
- Public - Available to everyone over the internet
- Hybrid - Mix of public and private
- Community - Several organizations share the same resources
## Desktop as a Service
- Basic application usage
	- Applications actually run on a remote server
	- Virtual Desktop Infrastructure (VDI), Desktop as a Service (DaaS)
	- Local device is a keyboard, mouse and screen
- Minimal operating system on the client
	- No huge memory or CPU needs
- Network connectivity
	- Big network requirement
	- Everything happens across the wire
## Designing the Cloud
- On-demand computing power
- Elasticity - scale up or down as needed
- Applications also scale
	- Scalability for large implementations
	- Access from anywhere
- Multitenancy
	- Many different clients are using the same cloud infrastructure
### Infrastructure as code
- Describe in infrastructure
	- Define servers, network, and applications as code
- Modify the infrastructure and create versions
	- The same way you version application code
- Use the description (code) to build other application instances
	- Build it the same way every time based on the code
- An important concept for cloud computing
	- Build a perfect version every time
### Orchstration
- Automation is the key to cloud computing
	- Services appear and disappear automatically, or at the push of a button
- Entire application instances can be instantly provisioned
	- All servers, networks, switches, firewalls, and policies
- Instances can move around the world as needed
- The security policies should be part of the orchestration
	- As applications are provisioned, the proper security is automatically included
### Connecting to the cloud
- VPN
	- Site-to-site virtual private network
	- Encrypt through the Internet
- Virtual Private Cloud Gateway
	- Connects users on the Internet
- VPC Endpoint
	- Direct connection between cloud provider networks
### VM sprawl avoidance
- Click a button
	- You've built a server
	- Or multiple servers, networks and firewalls
- It becomes almost too easy to build instances
	- This can get out of hard very quickly
- The virtual machines are sprawled everywhere
	- You aren't sure which VMs are related to which applications
	- It becomes extremely difficult to deprovision
- Formal process and detailed documentation
	- You should have information on every virtual object
### VM escape protection
- The virtual machine is self-contained
	- There's no way out (usually)
- Virtual machine escape
	- Break out of the VM and interact with the host operating system or hardware
- Once you escape the VM, you have great control
	- Control the host and control other guest VMs
- This would be a huge exploit
	- Full control of the virtual world
![Pasted_image_20240606155857](//assets/Pasted_image_20240606155857.webp)


