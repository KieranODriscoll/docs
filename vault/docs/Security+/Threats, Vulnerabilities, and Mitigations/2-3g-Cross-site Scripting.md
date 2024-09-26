# 2.3g - Cross-site Scripting
## XSS
- Originally called cross-site because of browser security flaws
	- Information from one site could be shared with another
- One of the most common web app vulnerabilities
	- Takes advantage of the trust a user has for a site
	- Complex and varied
- XSS commonly uses JavaScript
- Characteristics
	- Exploits the trust a user's web browser has in a website
	- A malicious script is injected into a trusted website
	- User's browser executes attacker's script
## Non-persistent (reflected) XSS attack
- Web site allows scripts to run in user input
	- Search box is a common source
- Attacker emails a link that takes advantage of this vulnerability
	- Runs a script that sends credentials/session IDs/cookies to the attacker
- Script embedded in URL executes in the victim's browser
	- As if it came from the server
- Attacker uses credentials/session IDs/cookies to steal victim's information without their knowledge
## Persistent (stored) XSS attack
- Attacker posts a message to a social network
	- Includes the malicious payload
- It's now "persistent"
	- Everyone gets the payload
- No specific target
	- All viewers of the page
- For social networking, this can spread quickly
	- Everyone who views the message can have it posted to their page
	- Where someone else can view it and propagate it further
## Hacking a Subaru
- June 2017, Aaron Guzman
- When authenticating with Subaru, users get a token
	- This token never expired
- A valid token allowed any service request
	- Even adding your email address to someone else's account
	- Now you have full access to someone else's car
- Web front-end included an XSS vulnerability
	- A user clicks a malicious link, and you have their token
## Protecting against XSS
- Be careful when clicking untrusted links
	- Never blindly click in your email inbox
- Consider disabling JavaScript
	- Or control with an extension
	- This offers limited protection
- Keep your browser and applications updated
- Validate unput
	- Don't allow users to add their own scripts to an input field
![](Pasted%20image%2020240908123608.png)