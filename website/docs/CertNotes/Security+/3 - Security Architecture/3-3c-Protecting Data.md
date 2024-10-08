# 3.3c - Protecting Data
## Geographic Restrictions
- Network location
	- Identify based on IP subnet
	- Can be difficult with mobile devices
- Geolocation - determine a user's location
	- GPS - mobile devices, very accurate
	- 802.11 wireless, less accurate
	- IP address, not very accurate
- Geofencing
	- Automatically allow or restrict access when the user is in a particular location
	- Don't allow this app to run unless you're near the office
- Pertain to policies that limit where data can be stored or accessed based on geography
## Protecting data
- A primary job task
	- An organization is out of business without data
- Data is everywhere
	- On a storage drive, on the network, in a CPU
- Protecting the data
	- Encryption, security policies
- Data permissions
	- Not everyone has the same access
## Encryption
- Encode information into unreadable data
	- Original information is plaintext, encrypted form is ciphertext
- This is a two-way street
	- Convert between one and the other
	- If you have the proper key
- Confusion
	- The encrypted data is drastically different than the plaintext
## Hashing
- Represent data as a short string of text
	- A message digest, a fingerprint
- One-way trip
	- Impossible to recover the original message from the digest
	- Used to store passwords / confidentiality
- Verify a downloaded document is the same as the original
	- Integrity
- Can be a digital signature
	- Authentication, non-repudiation, and integrity
	- Will not have a collision (hopefully)
	- Different messages will not have the same hash
## Obfuscation
- Obfuscate
	- Make something normally understandable very difficult to understand
- Take a perfectly readable code and turn it into nonsense
	- The developers keep the readable code and gives you the chicken scratch
	- Both sets of code perform exactly the same way
- Helps prevent the search for security holes
	- Makes it more difficult to figure out what's happening
	- But not impossible
## Masking
- A type of obfuscation
	- Hide some of the original data
- Protects PII
	- and other sensitive data
- May only be hidden from view
	- The data may still be intact in storage
	- Control the view based on permissions
- Many different techniques
	- Substituting, shuffling, encrypting, masking out, etc
## Tokenization
- Replace sensitive data with a non-sensitive placeholder
- Common with credit card processing
	- Use a temporary token during payment
	- An attacker capturing the card numbers can't use them later
- This isn't encrypting or hashing
	- The original data and token aren't mathematically related
	- No encryption overhead
## Segmentation
- Many organizations use a single data source
	- One large database
- One breach puts all of the data at risk
	- You're making it easy for the attacker
- Separate the data
	- Store it in different locations
- Sensitive data should have stronger security
	- The most sensitive data should be the most secure
## Permission restrictions
- Control access to an account
	- It's more than just username and password
	- Determine what policies are best for an organization
- The authentication process
	- Password policies
	- Authentication factor policies
	- Other considerations
- Permissions after login
	- Another line of defense
	- Prevent unauthorized access
