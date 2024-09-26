# 4.3c - Penetration Testing
## Penetration testing
- Pentest - simulate an attack
- Similar to vulnerability scanning
	- Except we actually try to exploit the vulnerabilities
- Often a compliance mandate
	- Regular penetration testing by a 3rd-party
- National Institute of Standards and Technology (NIST)
	- Technical guide to Information Security
	- Testing and Assessment
## Rules of engagement
- Important document
	- Defines purpose and scope
	- Makes everyone aware of the test parameters
- Type of testing and schedule
	- On-site physical breach, internal test, external test
	- Normal working hours, after 6PM only, etc
- The rules
	- IP address ranges
	- Emergency contacts
	- How to handle sensitive information
	- In-scope and out-of-scope devices or applications
## Exploiting vulnerabilities
- Try to break into the system
	- Be careful; this can cause a denial of service or loss of data
	- Buffer overflows can cause instability
	- Gain privilege escalation
- You may need to try many different vulnerability types
	- Password brute-force
	- Social engineering
	- Database injections
	- Buffer overflows
- You'll only be sure you're vulnerable if you can bypass security
	- If you can get through, the attackers can get through
## The process
- Initial exploitation
	- Get into the network
- Lateral movement
	- Move from system to system
	- The inside of the network is relatively unprotected
- Persistence
	- Once you're there, you need to make sure there's a way back in
	- Setup a backdoor, build user accounts, change or verify default passwords
- The pivot
	- Gain access to systems that would normally not be accessible
	- Use a vulnerable system as a proxy or relay
## Responsible disclosure program
- It takes time to fix a vulnerability
	- Software changes, testing, deployment, etc
- Bug bounty programs
	- A reward for discovering vulnerabilities
	- Earn money for hacking a system
	- Document the vulnerability to earn cash
- A controlled information release
	- Researcher reports the vulnerability
	- Manufacturer creates a fix
	- The vulnerability is announced publicly