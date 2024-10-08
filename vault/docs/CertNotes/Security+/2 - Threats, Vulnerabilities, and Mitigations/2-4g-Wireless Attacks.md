# 2.4g - Wireless Attacks
## Wireless Attacks
- Wireless deauthentication
	- A significant wireless denial of service attack
## 802.11 management frames
- 802.11 wireless includes a number of management frames
- Important for the operation of 802.11 wireless
	- How to find access points, manage QoS, associate/disassociate with an access point, etc
- Original wireless standards did not add protection for management frames
	- Sent in the clear
	- No authentication or validation
## Protecting against deauth attacks
- IEEE has already addressed the problem
	- 802.11w - July 2014
- Some of the important management frames are encrypted
	- Disassociate, deauthenticate, channel switch, announcements, etc
- Not everything is encrypted
	- Beacons, probes, authentication, association
- 802.11w is required for 802.11ac compliance
## Radio Frequency (RF) jamming
- Denial of Service
	- Prevent wireless communication
- Transmit interfering wireless signals
	- Decrease the signal-to-noise ratio at the receiving device
	- The receiving device can't head the good signal
- Sometimes it's not intentional
	- Interference, not jamming
	- Microwave oven, fluorescent lights
- Jamming is intentional
	- Someone wants your network to not work
## Wireless jamming
- Many different types
	- Constant, random bits / constant, legitimate frames
	- Data sent at random times - random data and legitimate frames
	- Reactive jamming - only when someone else tries to communicate
- Needs to be somewhere close
	- Difficult to be effective from a distance
- Time to go fox hunting
	- You'll need the right equipment to hunt down the jam
	- Directional antenna, attenuator