# 4.6d - Password Security
## Password complexity and length
- Make your password strong
	- Resist guessing or brute-force attack
- Increase password entropy
	- No single words, no obvious passwords
	- Mix upper and lower case letters, and special characters
- Stronger passwords are commonly at least 8 characters
	- These requirements change as processing speeds get faster
	- Consider a phrase or set of words
## Password age and expiration
- Password age
	- How long since a password was modified
- Password expiration
	- Password works for a certain amount of time
	- After expiration, password does not work
	- System remembers password history, requires unique passwords
- Critical systems might change more frequently
## Password managers
- Important to use different passwords for each account
	- Remembering all of them would be impractical
- Store all your passwords in a single database
	- Encrypted, protected
	- Can include multifactor tokens
- Built-in to many operating systems
	- And some browsers
- Enterprise password managers
	- Centralized management and recovery options
## Passwordless Authentication
- Many breaches are due to poor password control
	- Weak passwords, insecure implementation
- Authentication without a password
	- This solves many password management issuess
- You may already be passwordless
	- Facial recognition, security key, etc
- Passwordless may not be the primary authentication method
	- Used with a password or additional factors
## Just-in-time permissions
- In many organizations, the IT team is assigned administrator/root elevated account rights
	- This would be a great account to attack
- Grant admin access for a limited time
	- No permanent administrator rights
	- The principle of least privilege
- A breach user account never has elevated rights
	- Narrow the scope of a breach
- Request access from a central clearinghouse
	- Grants or denies based on predefined security policies
- Password vaulting
	- Primary credentials are stored in a password vault
	- The vault controls who gets access to credentials
- Accounts are temporary
	- Just-in-time process creates a time-limited account
	- Administrator receives ephemeral credentials
	- Primary passwords are never released
	- Credentials are used for one session than deleted