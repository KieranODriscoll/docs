# 4.1e - Application Security
## Secure coding concepts
- A balance between time and quality
	- Programming with security in mind is often secondary
- Testing, testing, testing
	- The QA process
- Vulnerabilities will eventually be found
	- And exploited
## Input validation
- What is the expected input?
	- Validate actual vs expected
- Document all input methods
	- Forms, fields, type
- Check and correct all input (normalization)
	- A zip code should by only X characters long with a letter in the X column
	- Fix any data with improper input
- The fuzzers will find what you missed
	- Don't give them an opening
## Secure cookies
- Information stored on your computer by the browser
- Used for tracking, personalization, session management
	- Not executable, not generally a security risk
	- Unless someone gets access to them
- Secure cookies have a Secure attribute set
	- Browser will only send it over HTTPS
- Sensitive information should not be saved in a cookie
	- This isn't designed to be secure storage
## Static code analyzers
- Static Application Security Testing (SAST)
	- Help to identify security flaws
- Many security vulnerabilities found easily
	- Buffer overflows, database injections, etc
- Not everything can be identified through analysis
	- Authentication security, insecure cryptography, etc
	- Don't rely on automation for everything
- Still have to verify each finding
	- False positives are an issue
## Code signing
- An application is deployted
	- Users run application executable or scripts
- So many security questions
	- Has the application been modified in any way?
	- Can you confirm that the application was written by a specific developer
- The application code can be digitally signed by the developer
	- Asymmetric encryption
	- A trusted CA signs the developer's public key
	- Developer signs the code with their private key
	- For internal apps, use your own CA
## Sandboxing
- Applications cannot access unrelated resources
	- They play in their own sandbox
- Commonly used during development
	- Can be a useful production technique
- Used in many different deployments
	- Virtual machines
	- Mobile devices
	- Browser iframes (Inline frames)
	- Windows User Account Control (UAC)
## Application security monitoring
- Real-time information
	- Application usage, access demographics
- View blocked attacks
	- SQL injection attempts, patched vulnerabilities
- Audit the logs
	- Find the information gathering and hidden attacks
- Anomaly detection
	- Unusual file transfers
	- Increase in client access
