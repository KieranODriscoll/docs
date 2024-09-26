# 2.4h - On-path Attacks
## On-path network attack
- Formerly known as a man-in-the-middle attack
- Redirects your traffic
	- Then passes it on to the destination
	- You never know your traffic was redirected
- ARP poisoning
	- On-path attack on the local IP subnet
	- ARP has no security
## On-path browser attack
- What if the middleman was on the same computer as the victim?
	- Malware/trojan does all the proxy work
	- Formerly known as man-in-the-browser
- Huge advantages for the attackers
	- Relatively easy to proxy encrypted traffic
	- Everything looks normal to the victim
- The malware in your browser wait for you to login to your bank