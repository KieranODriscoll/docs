# 2.2c - Watering Hole Attacks
## Watering Hole Attack
- What if your network was really secure?
	- You didn't even plug in that USB key from the parking lot
- The attackers can't get in
	- Not responding to phishing emails
	- Not opening any email attachments
- Have the mountain come to you
	- Go where the mountain hangs out
	- The watering hole
	- This requires a bit of research
## Executing the watering hole attack
- Determine which website the victim group uses
	- Educated guess - local coffee or sandwich shop
	- Industry-related sites
- Infect one of these third-party sites
- Infect one of these third-party sites
	- Site vulnerability
	- Email attachments
- Infect all visitors
	- But you're just looking for specific victims
	- Now you're in
### Because that's where the money is
- January 2017, Polish Financial Supervision Authority, National Banking and Stock Commission of Mexico, State-owned bank in Uruguay
	- The watering hole was sufficiently poisoned
- Vising the site would download malicious JavsScript files
	- But only to IP addresses matching banks and other financial institutions
## Watching the watering hole
- Defense-in-depth
	- Layered defense
	- It's never one thing
- Firewalls and IPS
	- Stop the network traffic before things get bad
- Anti-virus / Anti-malware signature updates
	- The Polish Financial Supervision Authority attack code was recognized and stopped by generic signatures in Symantec's anti-virus software
