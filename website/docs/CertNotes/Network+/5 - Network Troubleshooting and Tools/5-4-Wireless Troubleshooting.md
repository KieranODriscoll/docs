# 5.4 - Wireless Troubleshooting
## Wireless Performance
- Performance can vary
	- The wireless spectrum is unforgiving
	- Many more variables in play
- Throughput
	- The amount of data successfully transferred through the wireless network
- Speed
	- The maximum bandwidth available
	- Is generally faster as you get closer to the antennas
- Distance
	- The user needs to be relatively close to the access points
## Wireless Signals
- RSSI (Received Signal Strength Indication)
	- The strength of a received radio signal
- Measured in decibel-milliwatts (dBm)
	- The number of decibels (dB) with reference to one milliwatt (mW)
- Shown as a negative number on a log scale
	- Closer to zero is better
	- -50dBm is excellent
	- -70dBm is good
	- -80dBm and smaller is low
## Wireless survey tools
- Signal coverage
- Potential interference
- Built-in tools
- 3rd-party tools
- Spectrum analyzer
	- Measure the magnitude of an input signal's frequency.
## Wireless signals
- EIRP (Effective isotropic radiated power)
	- The radiated signal strength
	- Transmit strength + antenna gain - cable loss
- In the US, transmission power is regulated by the FCC
	- For 2.4GHz, max EIRP is +36 dBm or 4W
	- Varies based on connections and frequencies used
- Sometimes configurable on the access point
	- Equipment owner is responsible for managing EIRP
## Omnidirectional antennas
- One of the most common
	- Included on most access points
- Signal is evenly distributed on all sides
	- Place the antennas in the middle
- Good choice for most environments
	- You need coverage in all directions
- No ability to focus the signal
	- A different antenna will be required
## Directional antennas
- Focus the signal
	- Increase distances
- Send and receive in a single direction
	- Focused transmission and listening
- Antenna performance is measured in dB
	- Double power every 3dB of gain
- Yagi antenna
	- Very directional and high gain
- Parabolic antenna
	- Focus the signal to a single point
- Often used to bridge a gap
	- Point to point
	- Antennas are placed at both ends
## Antenna configuration
- Polarization
	- The orientation of an antenna
	- Relative to the surface of the Earth
- Transmitting and receiving polarization should be the same
	- If polarization is offset, only part of the signal with be received
## AP association time
- Devices must associate with an access point
	- This can occur multiple times as a device roams
- Signal strength
	- Association is delayed or blocked due to low signal
- Wired network controller issue
	- Latency and firmware issues can affect association time
- Track association metrics
	- Gather from the management console or via SNMP
## Channel utilization
- There's a limited amount of frequency
	- Everyone can't talk at one time
	- Similar to a wired network
- An increasing number of wireless devices
	- They all want to talk
- Most access points can monitor utilization
	- A percentage of available air-time
	- When you hit 100%, you've used up all of your available wireless space
## Managing channel utilization
- Disable legacy, low speed support
	- Use the fastest possible speeds and configurations
- Check your channels
	- Avoid overlap between access points
- Adjust the output power
	- Avoid conflicts with other access points
	- Interference can steal valuable network time
- Split the network
	- You might need additional frequencies and access points
## Site surveys
- Determine existing wireless landscape
	- Sample the existing wireless spectrum
- Identify existing access points
	- You may not control all of them
- Work around existing frequencies
	- Layout and plan for interference
- Plan for ongoing site surveys
	- Things will certainly change
- Heat maps - identify wireless signal strengths
## Common Wireless Issues
### Overlapping channels
- Avoid interference from other access points
	- Use a wireless analyzer
### Attenuation
- Wireless signals get weaker as you farther from the antenna
	- The attenuation can be measured with a Wi-Fi analyzer
- Control the power output on the access point
	- Not always an option
- Use a receive antenna with a higher gain
	- Capture more of the signal
- Some power is lost in the antenna cable coax
	- Most applicable at higher frequencies
	- Also check for damaged cables, especially outside
### Wrong SSID
- Every access point has at least one
	- Service Set Identifier (SSID)
	- But did you connect to the right one?
- This can be more confusing than you might think
	- Public Wi-Fi Internet, Guest Internet, Internet
- Confirm the correct SSID settings
	- Should be listed in the current connection status
### Wrong passphrase
- Wireless authentication
	- Many different methos
- Required to connect to the wireless network
	- If not connected, check the authentication
- Shared passphrase
	- Common in a SOHO, not in the enterprise
- 802.1X
	- Used for the enterprise
	- Make sure the client is configured to use 802.1X
### Security Type mismatch
- Encryption on wireless is important
	- Make sure the client matches the access point
- This is much easier these days
	- Almost everything is at the level of WPA2/3
- Some legacy equipment may not be able to keep up
	- If you change the access point, you may not be able to support it
- Migrate all of your WEP to WPA2/3
### Incorrect antenna placement
- Interference - Overlapping channels
- Slow throughput
	- Data fighting to be heard through the interface
- Check access point locations and channel settings
	- A challenge for 2.4GHz , much easier for 5GHz
### Captive portal
- Authentication to a network
	- Common on wireless networks
- Access table recognizes a lack of authentication
	- Redirects your web access to a captive portal page
	- Use a username/password to authenticate
- Authentication timeout
	- May require re-authentication after an interval
- Portal is probably authenticating to an external database
	- Check the back-end RADIUS/LDAP/TACACS process
### Client dissociation
- A denial of service attack
	- Takes advantage of older 802.11 management frame transmission
- Device keeps dropping from the wireless network
	- Or never connects
- Frames can be clearly seen in a packet capture
	- Grab the 802.11 frame information with Wireshark
- Remove the device performing the disassociation
	- Or upgrade to a new 802.11 standard
