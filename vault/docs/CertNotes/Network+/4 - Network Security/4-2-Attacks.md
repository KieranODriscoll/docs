# 4.2 - Attacks
## Denial of Service
- Force a service to fail
	- Overload the service
- Take advantage of a design failure or vulnerability
	- Keep your systems patched
- Cause a system to be unavailable
	- Competition advantage
- Create a smokescreen for some other exploit
	- Precursor to a DNS spoofing attack
- Doesn't have to be complicated
	- Turn off the power
- A "friendly" DOS
	- Unintentional DoSing
		- It's not always a ne'er-do-well
	- Network DOS
		- Layer 2 loop without STP
	- Bandwidth DoS
		- Downloading multi-gigabyte Linux distributions over a DSL line
	- The water line breaks
		- Get a good shop vacuum
### Bots
- Robots
	- That's you
- Once your machine is infected, it becomes a bot
	- You may not even know
- How does it get on your computer?
	- Trojan Horse
	- You run a program or click an ad you THOUGHT was legit
	- OS or application vulnerability
- A day in the life of a bot
	- Sit around
	- Check in with the Command and Control (C&C or C2) server
	- Wait for instructions
### Botnets
- A group of bots working together
	- Nothing good can come from this
- Distributed Denial of service (DDoS)
	- The power of many
- Relay spam, proxy network traffic, distributed computer tasks
- Botnets are for sale
	- Rent time from the botnet owner
	- Not a long-term business proposition
### Stopping the bot
- Prevent the initial infection
	- OS and application patches
	- Anti-virus/anti-malware and updated signatures
- Identify an existing infection
	- On-demand scans
	- Network monitoring
- Prevent command and control (C&C)
	- Block at the firewall
	- Identify at the workstation with a host-based firewall or host-based IPS
## On-path Attacks
### On-path network attack
- How can an attacker watch without you knowing?
	- Formerly known as man-in-the-middle
- Redirects your traffic
	- Then passes it on to the destination
	- You never known your traffic was redirected
- ARP poisoning
	- ARP has no security
	- On-path attack on the local IP subnet
### DNS poisoning
- Modify the DNS server
	- Requires some crafty hacking
- Modify the client host file
	- The host file takes precedent over DNS queries
- Send a fake response to a valid DNS request
	- Requires a redirection of the original request or the resulting response
	- Real-time redirection
	- This is an on-path attack
### Other on-path attacks
- Get in the middle of the conversation and view or change information
	- Session hijacking
	- HTTPS spoofing
	- Wi-fi eavesdropping
- Encryption fixes most of these situations
	- You can't change what you can't see
## VLAN Hopping
- Define different VLANs
- You only have access to your VLAN
	- Good security best practice
- "Hop" to another VLAN - this shouldn't happen
- Two primary methods
	- Switch spoofing and double tagging
### Switch spoofing
- Some switches support automatic configuration
	- Is the switch port for a device, or is it a trunk?
- There's no authentication required
	- Pretend to be a switch
	- Send trunk negotiation
- Now you've got a trunk link to a switch
	- Send and receive from any configured VLAN
- Switch administrators should disable trunk negotiation
	- Administratively configure trunk interfaces and device/access interfaces
### Double tagging
- Craft a packet that includes two VLAN tags
	- Takes advantages of the "native" VLAN configuration
- The first native VLAN tag is removed by the first switch
	- The second "fake" tag is now visible to the second switch
	- Packet is forwarded to the target
- This is a one-way trip
	- Responses don't have a way back to the source host
- Don't put any devices on the native VLAN
	- Change the native VLAN ID
	- Force tagging of the native VLAN
- ![[Pasted image 20240612172827.png]]
## Spoofing
- Pretend to be something you aren't
	- Fake web server, fake DNS server, etc
- Email address spoofing
	- The sending address of an email isn't really the sender
- Caller ID spoofing
	- The incoming call information is completely
- On-path attacks
	- The person in the middle of the conversation pretends to be both endpoints
### MAC spoofing
- Your ethernet device has a MAC address
- A unique burned-in address
- Most drivers allow you to change this
- Changing the MAC address can be legitimate
	- Internet provider expects a certain MAC address
	- Certain applications require a particular MAC address
- It might not be legitimate
	- Circumvent MAC-based ACLs
	- Fake-out a wireless address filter
- Very difficult to detect
	- How do you know its not the original device?
### IP address spoofing
- Take someone else's IP address
	- Actual device
	- Pretend to be somewhere you are not
- Can be legitimate
	- Load balancing
	- Load testing
- May not be legitimate
	- ARP poisoning
	- DNS amplification / DDoS
- Easier to identify than MAC address spoofing
	- Apply rules to prevent invalid traffic, enable switch security.
## Rouge Services
### Rogue DHCP server
- IP addresses assigned by a non-authorized server
	- There's no inherent security in DHCP
- Client is assigned an invalid or duplicate address
	- Intermittent connectivity, no connectivity
- Disable rogue DHCP communication
	- Enable DHCP snooping on your switch
	- Authorized DHCP server in Active Directory
- Disable the rogue
	- Renew the IP leases
### Rogue access points
- An unauthorized wireless access point
	- May be added by an employee or an attacker
	- Not necessarily malicious
	- A significant potential backdoor
- Very easy to plug in a wireless AP
	- Or enable wireless sharing in your OS
- Schedule a periodic survey
	- Walk around your building/campus
	- Use third-part tools / WiFi Pineapple
- Consider using 802.1X (Network Access Control)
	- You must authenticate, regardless of the connection type
### Wireless Evil Twins
- Looks legitimate, but actually malicious
	- The wireless version of phising
- Configure an access point to look like an existing network
	- Same (or similar) SSID and security settings/captive portal
- Overpower the existing access points
	- May not require the same physical location
- WiFi hotspots (and users) are easy to fool
	- And they're wide open
- You encrypt your communication right?
	- Use HTTPS and a VPN
	- Public access to public resources
## Malware and Ransomware
### Malware
- Malicious software
	- These can be very bad
- Gather information
	- Keystrokes
- Participate in a group
	- Controlled over the 'net
- Show you advertising
	- Big money
- Viruses and worms
	- Encrypt your data
	- Ruin your day
### Malware Types and Methods
- Viruses
- Crypto-malware
- Ransomware
- Worms
- Trojan Horse
- Rootkit
- Keylogger
- Adware/Spyware
- Botnet
### How you get malware
- These all work together
	- A worm takes advantage of a vulnerability
	- Installs malware that includes a remote access backdoor
	- Bot may be installed later
- Your computer must run a program
	- Email link - Don't click links
	- Web page pop-up
	- Drive-by download
	- Worm
- Your computer is vulnerable
	- Operating system - Keep your OS updated!
	- Applications - Check with the publisher
### Ransomware
- A particularly nasty malware
	- Your data is unavailable until you provide cash
- Malware encrypts your data files
	- Pictures, Documents, Music, Movies
	- Your OS remains available
	- They want you running, but not working
- You must pay the bad guys to obtain the decryption key
	- Untraceable payment system
	- An unfortunate use of public-key cryptography
## Password Attacks
### Plaintext / Unencrypted passwords
- Some applications store passwords "in the clear"
	- No encryption. You can read the stored password.
	- This is rare, thankfully
- Do not store passwords as plaintext
	- Anyone with access to the password file or database has every credential
- What to do if your application saves passwords as plaintext
	- Get a better application
### Brute force
- Try every possible password combination until the hash is matched
- This might take some tme
	- A strong hashing algorithm slows things down
- Brute force attacks - Online
	- Keep trying the login process
	- Very slow
	- Most accounts will lockout after a number of failed attempts
- Brute force the hash - Offline
	- Obtain the list of users and hashes
	- Calculate a password hash, compare it to a stored hash
	- Large computational resource requirement
### Hashing a password
- Hashes represent data as a fixed-length string of text
	- A message digest, or "fingerprint"
- Will not have a collision (hopefully)
	- Different inputs will not have the same hash
- One-way trip
	- Impossible to recover the original message from the digest
	- A common way to store passwords
#### The password file
- Different across operating systems and applications
	- Different hash algorithms
- ![](Pasted%20image%2020240613104741.png)
### Dictionary attacks
- Use a dictionary to find common words
	- Passwords are created by humans
- Many common wordlists available on the 'net
	- Some are customized by language or line of work
- The password crackers can substitute letters
	- p&ssw0rd
- This takes time
	- Distributed cracking and GPU cracking is common
- Discover passwords for common words
	- This won't discover random character passwords
## Deauthentication
- Starts as a normal day
	- Surfing along on your wireless network
		- then you aren't
	- and then it happens again, and again
- You may not be able to stop it
	- There's (almost) nothing you can do
	- Time to get a long patch cable
- Wireless disassociation
	- A significant wireless denial of service attack
### 802.11 management frames
- 802.11 wireless includes a number of management features
	- Frames that make everything work
	- you can never see them
- Important for the operation of 802.11 wireless
	- How to find access points, manage QoS, associate/disassociate with an access point, etc
- Original wireless standards did not add protection for management frames
	- Sent in the clear
	- No authentication or validation
### Protecting against disassociation
- IEEE has already addressed the problem
	- 802.11w - July 2014
- Some of the important management frames are encrypted
	- disassociate, deauthenticate, channel switch announcements, etc
- Not everything is encrypted
	- Beacons, probes, authentication, association
- 802.11w is required for 802.11ac compliance
	- This will roll out going forward
## Social Engineering
### Phising
- Social engineering with a touch of spoofing
	- Often delivered by email, text, etc
	- Very remarkable when well done
- Don't be fooled
	- Check the URL, and don't click links in email or text
- Usually there's something not quite right
	- Spelling, fonts, graphics
### Tricks and misdirection
- How are they so successful?
	- Digital slight of hand - it fools the best of us
- Typosquatting
	- A type of URL hijacking
	- Prepending - adding a letter in the beginning or something like that
- Pretexting
	- Lying to get information
	- Attacker is a character in a situation they create
	- Hi, we're calling from Visa regarding an automated payment to your utility service
### Tailgating and piggybacking
- Tailgating uses an authorized person to gain unauthorized access to a building
	- The attacker does not have consent
	- Sneaks through when nobody is looking
- Piggybacking follows the same process, but the authorized person is giving consent
	- Hold the door, hands are full with donuts
	- Sometimes you shouldn't be polite
- Once inside, there's little to stop you
	- Most security stops at the border
#### Watching for tailgating
- Policy for visitors
	- You should be able to identify anyone
- One scan, one person
	- A matter of policy or mechanically required
- Access Control Vestibule / Airlock
	- You don't have a choice
- Don't be afraid to ask
	- Who are you and why are you here
### Shoulder surfing
- You have access to important information
	- Many people want to see
	- Curiosity, industrial espionage, competitive advantage
- This is surprisingly easy
	- Airports / Flights
	- Hallway-facing monitors
	- Coffee shops
- Surf from afar
	- Binoculars / Telescopes
	- Easy in the big city
	- Webcam monitoring
### Preventing shoulder surfing
- Control your input
	- Be aware of your surroundings
- Use privacy filters
- Keep your monitor out of sight