# 2.1 - Common Threat Vectors
## Threat vectors
- A method used by the attacker
	- Gain access or infect to the target
	- Also called "attacker vectors"
- A lot of work goes into finding vulnerabilities in these vectors
	- Some are more vulnerable than others
- IT security professional spend their career watching these vectors
	- Protect existing vectors
	- Find new vectors
## Message-based vectors
- Phishing attacks
	- People want to click links
	- Links in an email, links send via text or IM
- Deliver the malware to the user
	- Attach it to the email
	- Scan all attachments, never launch untrusted links
- Social engineering attacks
	- Invoice scams, cryptocurrency scams
## Image-based vectors
- Easy to identify a text-based threat
	- It's more difficult to identify the threat in an image
- Some image formats can be a threat
	- The SVG (Scalable Vector Graphic) format
	- Image is described in XML (Extensible Markup Language)
- Significant Security Concerns
	- HTML injection
	- Javascript attack code
- Browsers must provide input validation
	- Avoids running malicious code
## File-based vectors
- More than just executables
	- Malicious code can hide in many places
- Adobe PDF
	- A file format containing other objects 
- ZIP/RAR files (or any compression type)
	- Contains many different files
- Microsoft Office
	- Documents with macros
	- Add-in files
## Voice call vectors
- Vishing
	- Phishing over the phone
- Spam over IP
	- Large-scale phone calls
- War dialing
	- It still happens
	- Practice of using technology to automatically scan a range of phone numbers in order to reveal connected devices such as computers, modems and office applications.
- Call tampering
	- Disrupting voice calls
## Removable device vectors
- Get around the firewall
	- The USB interface
- Malicious software on USB flash drives
	- Infect air gapped networks
	- Industrial systems, high-security services
- USB devices can act as keyboards
	- Hacker on a chip
- Data exfiltration
	- Terabytes of data walk out the door
	- Zero bandwidth used
## Vulnerable software vectors
- Client-based
	- Infected executable
	- Known (or unknown) vulnerabilities
	- May require constant updates
	- Drive-by download via web browser
	- Malicious macro
	- USB-based attack
	- Infected executable file
	- Malicious attachment in email application
- Agentless
	- No installed executable
	- Compromised software on the server would affect all users
	- Client runs a new instance each time
## Unsupported systems vectors
- Patching is an important prevention tool
	- Ongoing security fixes
- Unsupported systems aren't patched
	- There may not even be an option
- Outdated operating systems
	- Eventually, even the manufacturer won't help
- A single system could be an entry
	- Keep your inventory and records current
## Unsecure network vectors
- The network connects everything
	- Ease of access for the attackers
	- View all (non-encrypted) data
- Wireless
	- Outdated security protocols (WEP, WPA, WPA2)
	- Open or rogue wireless networks
- Wired
	- Unsecure interfaces - No 802.1X
- Bluetooth
	- Reconnaissance, implementation vulnerabilities
	- Bluejacking
		- Sending unsolicited messages over Bluetooth, DoS?
	- Bluesnarfing
		- Gaining unauthorized access to a bluetooth device
## Open service ports
- Most network-based services connect over a TCP or UDP port
	- An "open" port
- Every open port is an opportunity for the attacker
	- Application vulnerability or misconfiguration
- Every application has their own open port
	- More services expand the attack surface 
- Firewall rules
	- Must allow traffic to an open port
## Default credentials
- Most devices have default usernames and passwords
- The right credentials provide full control
	- Administrator access
- Very easy to find the defaults for your access point or router
## Supply chain vectors
- Tamper with the underlying infrastructure
	- Or manufacturing process
- Managed service providers (MSPs)
	- Access many different customer networks from one location
	- Company that needs IT services but lacks any IT personnel
	- MSSP - third-party vendor offering IT security management services
	- Threat vectors
		- Propagation of malware
		- Social engineering techniques
- Gain access to a network using a vendor
	- 2013 Target credit card breach
- Suppliers
	- Counterfeit networking equipment
	- Install backdoors, substandard performance and availability
	- 2020 - Fake Cisco Catalyst switches