# 2.4l - Cryptographic Attacks
## Cryptographic attacks
- You've encrypted data and sent it to another person
	- Is it really secure?
- That attacker doesn't have the combination (key)
	- So they break the safe (the cryptography)
- Finding ways to undo the security
	- There are many potential cryptographic shortcomings
	- The problem is often the implementation
## Birthday attack
- This is a hash collision
- Probability that someone shares the same birthday, 23 students is 50%, 30 is about 70%. This is where it gets its name
- A hash collision is the same hash value for two different plaintexts
- Find a collision through brute force
- The attacker will generate multiple versions of plaintext to match the hashes
	- Protect yourself wit ha large hash output size
## Collisions
- Hash digest are supposed to be unique
	- Different input data should not create the same hash
- MD5 hash has had collisions identified
## Downgrade attack
- Instead of using perfectly good encryption, use something that's not so great
	- Force the systems to downgrade their security
![Pasted_image_20240909141047](//assets/Pasted_image_20240909141047.webp)
