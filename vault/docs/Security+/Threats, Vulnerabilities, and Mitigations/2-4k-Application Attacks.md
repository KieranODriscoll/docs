# 2.4k - Application Attacks
## Injection Attacks
- Code injection
	- Adding your own information into a data stream
- Enabled because of bad programming
	- The application should properly handle input and output
- So many different injectable data types
	- HTML, SQL, XML, LDAP, etc
## SQL injection
- SQL - Structured Query Language
	- The most common relational database management system language
- SQL injection (SQLi)
	- Put your own SQL requests into an existing application
	- Your application shouldn't allow this
- Can often be executed in a web browser
	- Inject in a form or field
## Buffer Overflows
- Overwriting a buffer of memory
	- Spills over into other memory areas
- Developers need to perform bounds checking
- Not a simple exploit
	- Takes time to avoid crashing things
	- Takes time to make it do what you want
- A really useful buffer overflow is repeatable
	- Which means that a system can be compromised
## Replay attack
- Useful information is transmitted over the network
- Need access to the raw network data
	- Network tap, ARP poisoning
- The gathered information may help the attacker
- This is not an on-path attack
## Privilege escalation
- Gain higher-level access to a system
	- Exploit a vulnerability
	- Might be a bug or design flaw
- Higher-level access means more capabilities
	- This commonly is the highest-level access
- These are high-priority vulnerability patches
- Horizontal privilege escalation
	- User A can access user B resources
### Mitigating privilege escalation
- Patch quickly - fix the vulnerability
- Updated anti-virus/anti-malware software
	- Block known vulnerabilities
- Data Execution Prevention
	- Only data in executable areas can run
- Address space layout randomization
	- Prevent a buffer overrun at a known memory address
	- Elevation of privilege vulnerability
## Cross-site requests
- Cross-site requests are common and legitimate
### The client and the server
- Website pages consist of client-side code and server-side code
- Client side
	- Renders the page on the screen (HTML, Javascript)
- Server side
	- Performs requests for the client
### Cross-site request forgery
- One-click attack, session riding
	- XSRF, CSRF
		- Characteristics
			- Website executes attacker's requests
			- A user is tricked by an attacker in submitting unauthorized web requests
			- Exploits the trust a website has in the user's web browser
- Takes advantage of the trust that a web application has for the user
	- The website trusts your browser
	- Requests are made without your consent or knowledge
- Significant web application oversight
	- The application should have anti-forgery techniques added
	- Usually a cryptographic token to prevent a forgery
- ![[Pasted image 20240909140643.png]]
## Directory traversal
- Directory traversal / Path traversal
	- Read files from a web server that are outside of the website's file directory
	- Users shouldn't be able to browser the Windows folder
- Web server software vulnerability
	- Won't stop users from browsing past the web server root
- Web application code vulnerability
	- Take advantage of badly written code
