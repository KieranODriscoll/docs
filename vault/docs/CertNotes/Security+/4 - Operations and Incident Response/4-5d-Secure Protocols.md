# 4.5d - Secure Protocols
## Unencrypted network data
- Network traffic is important data
	- Everything must be protected
- Some protocols aren't encrypted
- Verify with a packet capture
	- View everything sent over the network
## Protocol selection
- Use a secure application protocol
	- Built-in encryption
- A secure protocol may not be available
	- This may be a deal-breaker
## Port selection
- Secure and insecure application connections may be available
	- It's common to run secure and insecure on different ports
- HTTP and HTTPS
	- Clear vs Encrypted web browsing
	- HTTP: Port 80
	- HTTPS: Port 443
- The port number does not guarantee security
	- Confirm the security features are enabled
	- Packet captures may be necessary
- ![](Pasted%20image%2020240917172649.png)
## Transport method
- Don't reply on the application
	- Encrypt everything over the current network transport
- 802.11 Wireless
	- Open access point: No transport-level encryption
	- WAP3: All user data is encrypted
- Virtual Private Network (VPN)
	- Create an encrypted tunnel
	- All traffic is encrypted and protected
	- Often requires third-party services and software