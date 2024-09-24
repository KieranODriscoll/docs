# 1.4b - Encrypting Data
## Encrypting Store Data
- Protect data on storage devices
	- SSD, Hard drive, USB, cloud storage, etc
	- This is data at rest
- Full-disk and partition/volume encryption
	- Bitlocker, FileVault, etc
- File encryption
	- EFS (encrypting file system), third-party utilities
	- MS Windows operating system that enables individual files or folders to be encrypted with the use of public keys
- Self-encrypting drive (SED)
	- data storage device that comes equipped with hardware-level encryption functionality
- PGP (Pretty good privacy)
	- Specifically designed for implementing encryption algorithms to secure data communication and storage
	- Communicate securely by decrypting and encrypting messages, authenticating messages through digital signatures and encrypting files
- GPG
	- Specifically designed for implementing encryption algorithms to secure data communication and storage
	- GnuPG or GNU Privacy Guard
## Database Encryption
- Protecting stored data
	- And the transmission of that data
- Transparent encryption
	- Encrypt all database information with a symmetric key
- Record-level encryption
	- Encrypt individual columns
	- Use separate symmetric keys for each column
## Transport Encryption
- Protect data traversing the network
	- You're probably doing this now
- Encrypting in the application
	- Browsers can communicate using HTTPS
- VPN (Virtual Private Network)
	- Encrypts all data transmitted over the network, regardless of the application
	- Client-based VPN using SSL/TLS
	- Site-to-site VPN using IPSec
## Encryption Algorithms
- There are many, many different ways to encrypt data
	- The proper "formula" must be used during encryption and decryption
- Both sides decide on the algorithm before encrypting the data
	- The details are often hidden from the end user
- There are advantages and disadvantages between algorithms
	- Security level, speed, complexity of implementation, etc
## Cryptographic Keys
- There's very little that isn't known about the cryptographic process
	- The algorithm is usually a known entity
	- The only thing you don't know is the key
- The key determines the output
	- Encrypted data
	- Hash value
	- Digital signature
- Keep your key private!
	- It's the only thing protecting your data
- 
## Key lengths
- Larger keys tend to be more secure
	- Prevent brute-force attacks
	- Attackers can try every possible key combination
- Symmetric encryption
	- 128-bit or larger symmetric keys are common
	- These numbers get larger and larger as time goes on
- Asymmetric encryption
	- Complex calculations of prime numbers
	- Larger keys than symmetric encryption
	- Common to see key lengths of 3072 bits or larger
## Key stretching
- A weak key is a weak key
	- By itself, its not very secure
- Make a weak key stronger by performing multiple processes
	- Hash a password, hash the hash of the password and continue
	- Key stretching, key strengthening
- Brute force attacks would require reversing each of those hashes
	- The attacker has to spend more time, even though the key is small
- Repeatedly hashing the password to make it more random and longer than it originally appeared
- Should make the key more time consuming to break