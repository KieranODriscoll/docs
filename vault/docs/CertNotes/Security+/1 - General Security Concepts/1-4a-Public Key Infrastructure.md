# 1.4a - Public Key Infrastructure
## Public Key Infrastructure
- Policies, procedures, hardware, software, people
	- Digital Certificates: create, distribute, manage, store, revoke
- This is a big, big endeavor
	- Lots of planning
- Also refers to the binding of public keys to people or devices
	- The certificate authority
	- It's all about trust
## Symmetric encryption
- A single, shared key
	- Encrypt with the key
	- Decrypt with the same key
	- If it gets out, you'll need another key
- Secret Key Algorithm
	- A shared secret
- Doesn't scale very well
	- Can be challenging to distribute
- Very fast to use
	- Less overhead than asymmetric encryption
	- Often combined with asymmetric encryption
- Symmetric ciphers
	- AES, DES, IDEA, RC4
## Asymmetric encryption
- Public Key Cryptography
	- Two (or more) mathematically related keys
- Private key
	- Keep this private
- Public key
	- Anyone can see this key
	- Give it away
- The private key is the only key that can decrypt data encrypted with the public key
	- You can't derive the private key from the public key
- Asymmetric ciphers
	- DHE, ECC, RSA.
## The key pair
- Asymmetric encryption
	- Public key cryptography
- Key generation
	- Build both the public and private key at the same time
	- Lots of randomization
	- Large prime numbers
	- Lots and lots of math
- Everyone can have the public key
	- Only Alice has the private key
## Key escrow 
- Someone else hold your decryption keys
	- Your private keys are in the hands of a 3rd party
	- This may be within your own organization
- This can be a legitimate business arrangement
	- A business might need access to employee information
	- Government agencies may need to decrypt partner data
- Controversial?
	- Of course
	- But may still be required
- System in which a copy of a cryptographic key is given to a third party
- Allows for recovery of keys if they are lost
## It's all about the process 
- Need clear process and procedures
	- Key are incredibly important pieces of information
- You must be able to trust your 3rd-party
	- Access to the keys is at the control of the 3rd-party
- Carefully controlled conditions
	- Legal proceedings and court orders

![](Pasted%20image%2020240905145154.png)
## Public Key Infrastructure Trust Models
- Single CA
- Hierarchical model (root + intermediate CAs)
- Mesh model (cross-certifying CAs)
- Web of trust (All CAs function as root CAs)
- Chain of trust model (Multiple CAs in a sequential chain)
- Bridge model (Cross-certifying between separate PKIs)
- Hybrid model (combining aspects of different models)
