# 2.4e - Denial of Service
## Denial of service
- Force a service to fail
	- Overload the service
- Take advantage of a design failure or vulnerability
	- Keep your systems patched
- Cause a system to be unavailable
- Create a smokescreen for some other exploit
	- Precursor to a DNS spoofing attack, etc
- Doesn't have to be complicated
### A "friendly" DOS
- Unintentional DoSing
	- It's not always a ne'er-do-well
- Network DoS - Layer 2 loop without STP
- Bandwidth DoS
	- Downloading multi-gigabyte over a DSL line
- The water line breaks
## Distributed Denial of Service (DDoS)
- Launch an army of computer to bring down a service
- Coordinated attack
- Asymmetric threat
	- Attacker may have fewer resources than the victim
### DDoS reflection and amplification
- Turn your small attack into a big attack
	- Often reflected off another device or service
	- An increasingly common network DDoS technique
	- Uses protocol with little or no authentication or checks
		- NTP, DNS, ICMP are examples
