# 2.4 - Wireless
## Wireless Standards
- Wireless networking (802.11)
- Managed by the IEEE LAN/MN Standards Committee (IEEE 802)
### 802.11a
- One of original 801.11 wireless standard
	- October 1999
- Operates in the 5 GHz range
- 54 megabits per second
- Smaller range than 802.11b
	- Higher frequency is absorbed by objects in the way
	- Many rules-of-thumb calculate 1/3rd the range of 802.11b or 802.11g
- Not commonly seen today
- 10 MHz channel bandwidth
### 802.11b
- Also an original 802.11 standard
	- October 1999
- Operates in the 2.4 GHz range
- 11 megabits per second
- Better range than 802.11a
	- Less absorption problems
- More frequency conflict
	- Baby monitors, cordless phones. microwaves
- Not commonly seen today
- 22 MHz channel bandwidth
### 802.11g
- An "upgrade" to 802.11b - June 2003
- Operates in the 2.4 GHz range
- 54 megabits per second
- Backwards-compatible with 802.11b
- Same 2.4 GHz frequency conflict problems as 802.11b
- 20 MHz channel bandwidth
### 802.11n (Wifi 4)
- The update to 802.11g, 802.11b, and 802.11a
	- October 2009
- Operates at 5GHz and/or 2.4GHz
	- 40 MHz channel widths
- 600 megabits per second
	- 40 MHz mode and 4 antennas
- 802.11n uses MIMO
	- Multiple-input multiple-output
	- Multiple transmit and receive antennas
- 20MHz/40MHz channel bandwidth
### 802.11ac
- January 2013
- Improvement over 802.11n
- Operates at the 5GHz band
	- Less crowded, more frequencies
	- Up to 160MHz channel bandwidth
- Increased channel bonding - Larger bandwidth usage
	- Commonly used in IEEE 802.11 implementations in which two adjacent channels within a given frequency band are combined to increase throughput between two or more wireless devices
- Denser signaling modulation  faster data transfer
- Eight MU-MIMO streams
	- Twice as many streams as 802.11n
	- Nearly 7 gigabits per second
### 802.11ax (Wifi 6)
- Approved February 2021
- Successor to 802.11ac/Wifi 5
- Operates at 5GHz and/or 2.4GHz
	- 20, 40, 80, 160 MHz channel widths
- 1,201 megabits per second per channel
	- A relatively small increase in throughput
	- Eight bi-directional MU-MIMO streams
- Orthogonal frequency-division multiple access (OFDMA)
	- Works similar to cellular communication
	- Improves high-density installations
![Pasted_image_20240608132107](//assets/Pasted_image_20240608132107.webp)
## Wireless Technologies
### 802.11 Technologies
![Pasted_image_20240608132925](//assets/Pasted_image_20240608132925.webp)
- Frequency
	- 2.4GHZ or 5GHz
	- sometimes both
- Channels
	- Groups of frequencies, numbered by the IEEE
	- Non-overlapping channels would be necessary
- Bandwidth
	- Amount of frequency in use
	- Is the maximum rate of data transfer across a given network. More of a theoretical concept that measures how much data can be transferred in ideal conditions
	- 20 MHz, 40 MHz, 80 MHz, 160 MHz
### 802.11 Channel Bandwidths
- 802.11a (20MHz), 802.11b (22MHz), 802.11g(20MHz)
- 802.11n (20, 40, 80 MHz)
	- Increase bandwidth with bonded channels
	- In 2.4 GHz, a 40 MHz channel uses over 80% of the available bandwidth
- 802.11ac
- 20, 40, 80, 80+80, 160 MHz
	- 40 for 802.11n stations, 80 required for 802.11ac stations
	- 160 MHz optional (contiguous channels or no contiguous)
- 802.11ax
	- 20, 40, 80, 80+80, 160 MHz
	- Similar bandwidths to 802.11ac
### Independent Basic Service Set (IBSS)
- Two devices communicate directly to each other using 802.11
	- No access point required
- AD hoc
	- Created for a particular purpose without any previous planning
	- Without an AP
- Temporary or long-term communication
	- Connect to a device with an ad hoc connection
	- Configure it with the access point settings and credentials
### SSID and BSSID
- Every wireless network needs a name
	- SSID (Service Set Identifier)
- There might be multiple access points supporting an SSID
	- How does your computer tell them apart?
	- The hardware address of an access point is a BSSID (Basic Service Set Identifier)
	- The MAC (Media Access Control) address
### Extending the network
- Most organizations have more than one access point
	- Tens or hundreds
- Wireless network names can be used across access points
	- Makes it easier to roam from one part of the network to another
- The network name shared across access points is an ESSID (Extended Service Set Identifier)
- Your devices automatically roams when moving between access points
	- You don't have to manually reconnect
### Counting Antennas
- New technologies were added to
	- 802.11n, 802.11ac, 802.11ax
	- Send multiple streams of information over the same frequency at the same time
	- 802.11n - MIMO
	- 802.11ac - Downstream MU-MIMO (Multi-user MIMO)
	- 802.11ax - Down and Upstream MU-MIMO
- Number of antennas
	- Used to determine the n umber of available streams
	- (Antennas on the access point) x (antennas on the client): number of streams
	- 2x2:2, 3x3:2, 4x4:4
### Omnidirectional Antennas
- One of the most common
	- Included on most access points
- Signal is evenly distributed on all sides
- Good choice for most environments
	- You need coverage in all directions
- No ability to focus the signal
	- A different antenna required
### Directional antennas
- Focus the signal
	- Increased distances
- Send and receive in a single direction
	- Focused transmission and listening
- Antenna performance is measured in dB
	- Double power every 3dB of gain
- Yagi antenna
	- Very directional and high gain
	- point-to-point
- Parabolic antenna
	- Focus the signal to a single point
	- Works well outside
- Unidirectional
	- Broadcasts radio frequencies in a single direction
	- Focusing the broadcast signal in a single direction instead of all directions, making it stronger
	- point-to-point
- Bidirectional
	- Broadcasts radio frequencies in two directions
- Patch Antenna
	- Low profile antenna that can be mounted to a surface, can be omnidirectional, bidirectional or unidirectional
- 5dB for example would not be sufficient for an outdoor wireless connection
## Wireless Encryption
### Securing a wireless network
- An organization's wireless network can contain confidential information
	- Not everyone is allowed access
- Authenticate the users before granting access
	- Who gets access to the wireless network
	- Username, password, multi factor
- Ensure all communication is confidential
	- Encrypt the wireless data
- Verify the integrity of all communication
	- The received data should be identical to the original sent data
	- A Message integrity check (MIC)
### WPA (Wi-fi Protected Access)
- 2002: WPA was the replacement for serious cryptographic weakness in WEP
	- Wireless Equivalent Privacy
	- **Don't use WEP**
- Needed a short-term bridge between WEP and whatever would be the successor
	- Run on existing hardware
- WPA: RC4 with TKIP (Temporal Key Integrity Protocol)
	- Initialization Vector (IV) is larger and an encrypted hash
	- Every packet gets a unique 128-bit encryption key
### Wireless Encryption
- All wireless computer are radio transmitters and receivers - Anyone can listen in
- Solution: Encrypt the data
	- Everyone has an encryption key
- Only people with the right key can transmit and listen
	- WPA2 and WPA3
### WPA2 and CCMP
- Wi-fi Protected Access II
- CCMP Block cipher mode
	- Counter mode with cipher clock chaining
	- Message authentication code protocol, or
	- Counter/CBC-MAC protocol
- CCMP security services
	- Data confidentiality with AES encryption
	- Message Integrity Check (MIC) with CBC-Mac
### WPA3 and GCMP
- Wi-fi Protected Access 3
- GCMP block cipher mode
	- Galois/Counter Mode Protocol
	- Stronger encryption than WPA2
- GCMP security services - Data confidentiality with AES
	- Message Integrity Check with Galois Message Authentication Code (GMAC)

### The WPA2 PSK problem
- WPA2 has a PSK bruite-froce problem
- Listen to the four-way handshake
- Some methods can derive the PSK hash without the handshake
- Capture the hash
- With the hash, attackers can brute force the pre-shared key (PSK)
- This has become easier as technology imprives
	- A weak PSK is easier to brute force
	- GPU processing speeds
	- Cloud-based password cracking
- Once you have the PSK, you have everyone's wireless key
	- No forward secrecy
### SAE
- WPA3 changes the PSK authentication process
	- Includes mutual authentication
	- Creates a shared session key without sending that key across the network
	- No more four-way handshakes, no hashes, no brute force attacks
	- Adds perfect forward secrecy
- Simultaneous Authentication of Equals (SAE)
	- A Diffie-Hellman derived key exchange with an authentication component
	- Everyone uses a different session key, even with the same PSK
	- An IEEE standard - the dragonfly handshake
### Wireless Security Modes
- Configure the authentication on your wireless access point / wireless router
- Open System - No authentication password is required
- WPA2/3-Personal / WPA2/3-PSK
	- WPA2 or WPA3 with a pre-shared key
	- Everyone uses the same 256-bit key
- WPA-2/3-Enterprise / WPA2/3-802.1X
	- Authenticate users individually with an authentication server (IE. RADIUS)
## Cellular Standards
### Cellular networks
- Mobile devices
- Separate land into "cells"
	- Antenna coverages a cell with certain frequencies
- 2G Networks
	- GSM - Global System for Mobile Communication
	- CDMA - Code Division Multiple Access
- Poor data support
	- Originally used circuit-switching
	- Minor upgrades for some packet-switching
#### GSM
- Global System for Mobile Communications
	- Mobile networking standard
- 90% of the market
	- Originally an EU standard - worldwide coverage
- Used by AT&T and T-Mobile in the US
	- Move your SIM card (Subscriber Identity Module) from phone to phone
- Original GSM standard used multiplexing
	- Everyone gets a little slice of time
- Time-division Multiplexing
	- Allows for two or more signals or bitstreams to be transferred in what appears to be simultaneous sub-channels in on communication channel but is physically taking turn.
	- Also used in ISDN or T-1 services to essentially share a single frequency or cable but pass multiple voice calls over it
#### CDMA
- Code Division Multiple Access
	- Everyone communicates that the same time
	- Each call uses a different code
	- The codes are used to filter each call on the receiving side
- Used by Verizon and Sprint
	- Handsets are controlled by the network provider
	- Not much adoption elsewhere
#### 3G Technology
- 3rd Generation
	- 1998
- Upgraded data connectivity over 2G
	- Incremental 3G updates improved speeds
	- Usually several megabits per second
- Bandwidth improvement allowed new functionality
	- GPS, Mobile television, video on demand, video conferencing
#### 4G and LTE
- Long Term Evolution (LTE) - A "4G" technology
	- Converged standard (GSM and CDMA providers)
	- Based on GSM and EDGE (Enhanced Data Rates for GSM Evolution)
	- Standard supports download rates of 150 Mbit/s
- LTE Advanced (LTE-A)
	- Standard supports download rates of 300 MBit/s
#### 5G
- Fifth generation cellular networking
	- Launched worldwide in 2020
- Signification performance improvements
	- At higher frequencies
	- Eventually 10 gigabits per second
	- Slower speeds from 100-900 Mbit/s
- Significant IoT impact
	- Bandwidth becomes less of a constraint
	- Large data transfers
	- Faster monitoring and notification
- Additional cloud processing
