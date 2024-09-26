# 4.5e - Email Security
## Email security challenges
- The protocols used to transfer emails include relatively few security checks
	- It's very easy to spoof an email
- Spoofing happens all the time
	- Check your spam folder
- The email looks as if it originated from an email, but did it really
- A reputable sender will configure email validation
	- Publicly available on the sender's DNS server
## Mail Gateway
- The gatekeeper
	- Evaluates the source of inbound emails messages
	- Blocks it at the gateway before it reaches the user
	- On-site or cloud-based
## Sender Policy Framework (SPF)
- SPF Protocol
	- Sender configures a list of all servers authorized to send emails for a domain
- List of authorized mail servers are added to a DNS TXT record
	- Receiving mail servers perform a check to see if incoming mail really did come from an authorized host
- Valuable in identifying which servers are authorized to send emails on behalf of a domain, does not cryptographically sign the emails for this assurance
## Domain Keys Identified (DKIM)
- A mail server digitally signs all outgoing mail
	- The public key is in the DKIM TXT record
- The signature is validated by the receiving mail servers
	- Not usually seen by the end user
- Can sign emails originating from their domain cryptographically
- Allows receivers to verify that an email claiming to be from the domain genuinely is
## DMARC
- Domain-based Message Authentication
	- Reporting and Conformance (DMARC)
	- An extension of SPF and DKIM
- The domain owner decides what receiving email servers should do with emails not validating using SPF and DKIM
	- That policy is written into a DNS TXT record
	- Accept all, spend to spam or reject the email
- Compliance reports are sent to the email administrator
	- The domain owner can see how emails are received
- The results of DKIM and SPF checks, but on its own, it doesn't cryptographically sign emails