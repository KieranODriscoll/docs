# 1.2b - Non-repudiation
## Non-repudiation
- You can't deny what you've said
	- There's no taking it back
- Sign a contract
	- Your signature adds non-repudiation
	- You really did sign the contract
	- Others can see your signature
- Adds a different perspective for cryptography
	- Proof of integrity
	- Proof of origin, with high assurance of authenticity
## Proof of integrity
- Verify data does not change
	- The data remains accurate and consistent
- In cryptography, we use a hash
	- Represent data as a short string of text
	- A message digest, a fingerprint
- If the data changes, the hash changes
	- If the person changes, you get a different fingerprint
- Don't necessarily associate data with an individual
	- Only tells you if the data has changed
- If you change one character somewhere in the file
	- The hash changes
- If the hash is different, something has changed
	- The data integrity has been compromised
## Proof of Origin
- Prove the message was not changed
	- Integrity
- Prove the source of the message
	- Authentication
- Make sure the signature isn't fake
	- Non-repudiation
- Sign with the private key
	- The message doesn't need to be encrypted
	- Nobody else can sign this
- Verify with the public key
	- Any change to the message will invalidate the signature
![Pasted_image_20240905131903](//assets/Pasted_image_20240905131903.webp)
