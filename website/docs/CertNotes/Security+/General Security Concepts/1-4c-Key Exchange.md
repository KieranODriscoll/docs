# 1.4c - Key Exchange
## Key Exchange
- A logistical challenge
	- How do you share an encryption key across an insecure medium without physically transferring the key?
- Out-of-band key exchange
	- Don't send the symmetric key over the 'net
	- Telephone, courier, in-person, etc
- In-band key exchange
	- It is on the network
	- Protect the key with additional encryption
	- Use asymmetric encryption to deliver a symmetric key
## Real-time encryption/decryption
- There's a need for fast security
	- Without compromising the security part
- Share a symmetric session key using asymmetric encryption
	- Client encrypts a random (symmetric) key with a server's public key
	- The server decrypts this shared key and uses it to encrypt data
	- This is the session key
- Implement session keys carefully
	- Need to be changed often (ephemeral keys)
	- Need to be unpredictable 
## Symmetric key from asymmetric keys
- Use public and private key cryptography to create a symmetric key
	- Math is powerful
![Pasted_image_20240905152247](//assets/Pasted_image_20240905152247.webp)
