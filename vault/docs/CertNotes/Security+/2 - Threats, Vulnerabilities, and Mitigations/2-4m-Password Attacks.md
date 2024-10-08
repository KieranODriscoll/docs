# 2.4 - Password Attacks
## Plaintext / unencrypted passwords
- Some applications store passwords unencrypted
- Do not store passwords as plaintext
	- Anyone with access to the password file or database has every credential
## Hashing a password
- Hashes represent data as a fixed-length string of text
	- A message digest, or fingerprint
- Will hopefully have no collision
- One way trip
	- Impossible to recover the original message from the digest
	- A common way to store passwords
## The password file
- Different across operating systems and applications
	- Different hash algorithms
## Spray attacks
- Try to login with an incorrect password, eventually you get locked out
- Attack an account with the top three or more passwords
	- If they don't work, move to the next account
	- No lockouts, no alarms, no alerts
## Brute force
- Try every possible password combination until the hash is matched
- This will take some time
	- Strong hashing algorithm slows things down
- Online attack:
	- Keep trying the login process
	- Very slow
	- Most accounts will lockout after a number of failed attempts
- Offline
	- Obtain the list of users and hashes
	- Calculate a password hash, compare it to a stored hash
	- Large computational resource requirements