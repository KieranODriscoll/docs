# 2.3l - Misconfiguration Vulnerabilities
## Open permissions
- Very easy to leave a door open
	- The hackers will always find it
- Increasingly common with cloud storage
	- Statistical chance of finding an open permission
- June 2017 - 14 million Verizon records exposed
	- Third-party left an Amazon S3 data repository open
	- Research found the data before anyone else
- Many, many other examples
	- Secure your permissions
## Unsecured admin accounts
- The Linux root account
	- The Windows Administrator or superuser account
- Can be a misconfiguration
	- Intentionally configuring an easy-to-hack password
- Disable direct login to the rout account
	- Use the su or sudo option
- Protect accounts with root or administrator access
	- There should not be a lot of these
## Insecure protocols
- Some protocols aren't encrypted
	- All traffic sent in the clear
	- Telnet, FTP, SMTP, IMAP
	- SMTPS is a deprecated TLS-based method for secure transmission of emails
	- SHHTP is a obsolete protocol used for secure data transfer over the web
- Verify with a packet capture
	- View everything sent over the network
- Use the encrypted versions - SSH, SFTP, IMAPS, etc
## Default settings
- Every application and network device has a default login
	- Not all of these are ever changed
- Mirai botnet
	- Takes advantage of default configurations
	- Takes over IoT devices
	- 60+ default configurations 
	- Cameras, routers, doorbells, garage door openers, etc
- Mirai released as open-source software
## Open ports and services
- Services will open ports
	- Important to manage access
- Often managed with a firewall
	- Manage traffic flows
	- Allow or deny based on port number or application
- Firewall rulesets can be complex
	- It's easy to make a mistake
- Always test and audit
	- Double and triple check
