# 2.3i - Virtualization Vulnerabilities
## Virtualization security
- Quite different than non-virtual machines
- Quantity of resources vary between VMs
- Many similarities to physical machines
	- Complexity adds opportunity for the attackers
- Virtualization
	- Local privilege escalations
	- Command injection
	- Information disclosure
## VM escape protection
- The virtual machine is self-contained
	- Should be no way out
- Virtual machine escape
	- Break out of the VM and interact with the host operating system or hardware
- Once you escape the VM, you have great control
	- Control host and control other guest VMs
- This would be a huge exploit
	- Full control of the virtual world
## Escaping the VM
- March 2017 - Pwn2Own Competition
- Javascript Engine bug in Microsoft Edge
	- Code execution in the Edge sandbox
- Windows 10 kernel bug
	- Compromise the guest operating system
- Hardware simulation bug in VMware
	- Escape to he host
- Patches were released soon afterwards
## Resource reuse
- The hypervisor manages the relationship between physical and virtual resources
	- Available RAM, storage space, CPU availability, etc
- These resources can be reused between VMs
	- Hypervisor host with 4GB of RAM
	- Supports 3 VMs with 2GB of RAM each
	- RAM is allocated and shared between VMs
- Data can inadvertently be shared between VMs
	- Time to update the memory management features
	- Security patches can mitigate the risk