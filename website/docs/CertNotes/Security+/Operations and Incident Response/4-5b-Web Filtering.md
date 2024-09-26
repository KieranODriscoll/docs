# 4.5b - Web Filtering
## Content filtering
- Control traffic based on data within the content
	- URL filtering, web category filtering
- Corporate control of outbound and inbound data
	- Sensitive materials
- Control of inappropriate content
	- Not safe for work
	- Parental controls
- Protection against evil
	- Anti-virus, anti-malware
## URL Scanning
- Allow or restrict based on Uniform Resource Locator
	- Also called a Uniform Resource Identifier (URI)
	- Allow list / Block list
- Managed by category
	- Auction, Hacking, Malware
	- Travel, Recreation, etc
- Can have limited control
	- URLs aren't the only way to surf
- Often integrated into a NGFW
	- Filters traffic based category or specific URL
## Agent based
- Install client software on the user's device
	- Usually managed from a central console
- Users can be located anywhere
	- The local agent makes the filtering decisions
	- Always-on, always filtering
- Updates must be distributed to all agents
	- Cloud-based updates
	- Update status shown at the console
## Proxies
- Sits between the users and the external network
- Receives the user requests and sends the request on their behalf (the proxy)
- Useful for caching information, access control, URL filtering, content scanning
- Applications may need to know how to use the proxy (explicit)
- Some proxies are invisible (transparent)
## Forward proxy
- A centralized "internal proxy"
	- Commonly used to protect and control user access to the Internet
	- allows or blocks traffic based on rules
	- Does not require agents installed on each client
## Block rules
- Based on specific URL
- Category of site content
	- Usually divided into over 50 different topics
	- Adult, Educational, Gambling, Government, Home and Garden, etc
- Different dispositions
	- Educational: Allow
	- Home and Garden: Allow and Alert
	- Gambling: Block
## Reputation
- Filter URLs based on perceived risk
	- A good reputation is allowed
	- A bad reputation is blocked
	- Risk: Trustworthy, Low risk, Medium risk, Suspicious, High risk
- Automated reputation
	- Sites are scanned and assigned a reputation
- Manual reputation
	- Managers can administratively assign a rep
- Add these dispositions to the URL filter
	- High risk: Block, Trustworthy: Allow
## DNS filtering
- Before connecting to a website, get the IP address
	- Perform a DNS lookup
- DNS is updated with real-time threat intelligence
	- Both commercial and public lists
- Harmful sites are not resolved
	- No IP address, no connection
- This works for any DNS lookup
	- Not just web filtering
