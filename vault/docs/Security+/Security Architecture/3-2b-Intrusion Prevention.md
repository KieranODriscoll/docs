# 3.2b - Intrusion Prevention
## Failure modes
- We hope for 100% uptime
	- Not realistic, something will eventually break
- Fail-open
	- When a system fails, data continues to flow
- Fail-closed
	- When a system fails, data does not flow
## Device connections
- Active monitoring
	- System is connected inline
	- Data can be blocked in real-time as it passes by
	- Intrusion prevention is commonly active
- Passive monitoring
	- A copy of the network traffic is examined using a tap or port monitor
	- Data cannot be blocked in real-time
	- Intrusion detection is commonly passive
## Intrusion Prevention System (IPS)
- Intrusion Prevention System
	- Watch network traffic
- Intrusions
	- Exploits against operating systems, applications, etc
	- Buffer overflows, cross-site scripting, other vulnerabilities
- Detection vs Prevention
	- Detection - Alarm or Alert
	- Prevention - Stop it before it gets into the network
![[Pasted image 20240913182354.png]]