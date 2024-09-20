# 5.2 - Wired Network Troubleshooting
## Cable Connectivity
### Using the right cable
- Speed / Bandwidth
	- Theoretical maximum data rate
	- Usually measured in bits per second
	- The size of the pipe
- Throughput
	- Amount of data transferred in a given timeframe
	- Usually measured in bits per second
	- How much water is flowing through the pipe
- Distance
	- Know the maximum distance
	- Varies based on copper, fiver, repeaters, etc
### Unshielded and shielded cable
- Abbreviations
	- U = Unshielded, S = Braided shielding, F = foil shielding
- (Overall cable) / (Individual pairs)TP
	- Braided shielding around the entire cable and foil around the pairs is S/FTP
	- Foil around the cable and no shielding around the pairs is F/UTP
### Plenum
- Plenum space
	- Building air circulation
	- Heating and air conditioning system
- Concerns in the case of a fire
	- Smoke and toxic fumes
- Worst-case planning
	- Important concerns for any structures
### Plenum-rated cable
- Traditional cable jacket
	- Polyvinyl chloride (PVC)
		- This PVC jacket when burning or smoldering releases hydrochloric acid and dioxin which are both toxic. For this reason, PVC cannot be used in-between the drop ceiling and the standard ceiling.
- Fire-rated cable jacket
	- Fluorinated ethylene polymer (FEP) or low-smoke polyvinyl chloride (PVC)
- Plenum-rated cable may not be as flexible
	- May not have the same bend radius
- Mandated to be installed in any air handling space, such as between a drop ceiling and the standard ceiling. 
- Riser-rated cabling is more expensive than plenum-rated cabling due to higher fire resistance requirements
- Riser-rated cabling has a higher fire resistance than plenum-rated cabling
- Riser-rated cabling can be used either in the plenum spaces or riser spaces
### Serial console cables
- D-subminiature or D-sub
	- The letter refers to the connector size
- Commonly used for RS-232
	- Recommended Standard 232
	- An industry standard since 1969
	- Standard for serial communication transmission of data
	- Signals connecting an DTE (data terminal equipment) such as a computer terminal and a DCE (data circuit-terminating equipment)
	- DB-9 connect is often found on a rollover or console cable and is used to connect a router to a laptop using the RS-232 serial transmission protocol for configuring a network device
- Serial communication standard
	- Built for modern communication
	- Used for modems, printers, mice, networking
- Now used as a configuration port
### "Rollover" cable
- Rolled cable, Cisco console cable
	- Yost cable
	- Serial cable "standard" proposed by Dave Yost
- A standard for RJ-45 to serial communication
- Used in conjunction with serial port connectors
![Pasted_image_20240613180128](//assets/Pasted_image_20240613180128.webp)
### Ethernet cross-over cables
- Connect to Ethernet devices without using a switch
	- Use your crossover cable
- Can be a good alternative to a console connection
	- You may not always have the right serial cable or connector
- Always carry a crossover cable
	- Or an adapter with the crossover
### Power over Ethernet(POE)
- Power provided on an Ethernet cable
	- One wire for both network and electricity
	- Phones, cameras, wireless access points
	- Useful in difficult-to-power areas
- Power provided at the switch
	- Built-in power - Endspans
	- In-line power injector - midspans
- Power modes
	- Mode A - Common-mode data pair power
	- Mode B - Power on the spare pare
	- 4-pair - Power on all four data pair
### PoE, PoE+, PoE++
#### POE: IEEE 802.3af-2003
- The original PoE specification
- Now part of the 802.3 standard
- 15.4 watts DC power, 350 mA max current
#### PoE+: IEEE 802.3at-2009
- Now part of the 802.3 standard
- 25.5 watts DC power, 600 mA max current
#### PoE++: IEEE 802.3bt-2018
- 51W (Type 3), 600 mA max current
- 71.3 (Type 4), 960 mA max current
- PoE with 10GBASE-T
## Wired Network Troubleshooting
### Attenuation
- Usually gradual
	- Signal strength diminishes over distance
	- Loss of intensity as signal moves through a medium
- Electrical signals through copper, light through fiber, Radio waves through the air
- Can also be caused by obstructions of the line of sight between antennas
### Decibels (dB)
- Signal strength ratio measures
	- One-tenth of a bel
	- Capital B for Alexander Graham Bell
- Logarithmic scale
	- Add and subtract losses and gains
- 3dB = 2x the signal
- 10 dB = 10x the signal
- 20 dB = 100x the signal
- 30 dB = 100x the signal
### dB loss symptoms
- No connectivity, no signal
- Intermittent connectivity
	- Just enough signal to sync the link
- Poor performance
	- Signal too weak
	- CRC errors, data corruption
- Test each connection
	- Test distance and signal loss
### Avoiding EMI and Interference
- Electromagnetic interference
- Cable handling
	- No twisting - don't pull or stretch
	- Watch your bend radius
	- Don't use staples, watch your cable ties
- EMI and Interference with copper cables
	- Avoid power cords, fluorescent lights, electrical systems, and fire prevention components
- Test after installation
	- You can find most of your problems before use
### Troubleshooting pin-outs
- Cables can foul up a perfectly good plan
	- Test your cables prior to implementation
- Many connectors look alike
	- Do you have a good cable mapping device?
- Get a good cable person - it's an art
### Incorrect pin-out
- Near and far pins in cables aren't where they are supposed to be
	- Pin 1 goes to pin 1, pin 2 to pin 2, etc
- Performance or connectivity issues
	- May drop from 1 gbit/sec to 100 mbit/sec
	- May not connect at all
### Bad ports
- Interface erros
	- May indicate bad cable or hardware problem
- Verify configurations
	- Speed, duplex, VLAN, etc
- Verify two-way traffic
	- End-to-end connectivity
### Interface configuration problems
- Poor throughput - Very consistent, easily reproducible
- No connectivity - No link light
- No connectivity - Link light and activity light
### Interface configuration
- Auto vs Manual configuration
	- Personal preference
- Light status - No light, no connection
- Speed - must be identical on both sides
- Duplex
	- If mismatched, speed will suffer
	- Increase in late collisions
### Duplex/speed mismatch
- Speed and duplex
	- Speed: 10 / 100 / 1000 / Auto
	- Duplex Half / Full / Auto
- Incorrect seed
	- Many switch configurations will auto-negotiate speed
	- Less than expected throughput
- Incorrect duplex
	- Again, the switch may auto-negotiate
	- Needs to match on both sides
	- A mismatch will cause significant slowdowns
	- Increase in Late collisions may indicate a duplex mismatch
### Opens and shorts
- A short circuit
	- Two connections are touching
	- Wires inside of a cable or connection
- An open circuit
	- A break in the connection
- Complete interruption
	- Can be intermittent
### Troubleshooting opens and shorts
- May be difficult to find
	- The wire has to be moved just the right way
	- Wiggle it here and there
- Replace the cable with the short or open
	- Difficult or impossible to repair
- Advanced troubleshooting with a TDR
	- Time Domain Reflectometer
### Incorrect transceivers
- Transceivers have to match the fiber
	- Single mode transceiver connects to single mode fiber
- Transceiver needs to match the wavelength
	- 850nm, 1310nm, etc
- Use the correct transceivers and optical fiber
	- Check the entire link
- Signal loss - Dropped frames, missing frames
### Reversing transmit and receive
- Wiring mistake
	- Cable ends
	- Punchdowns
- Easy to find with a wire map
	- 1-3, 2-6, 3-1, 6-2
	- Simple to identify
- Some network interfaces will automatically correct (Auto-MDIX)
### TX/RX reversal troubleshooting
- No connectivity
	- Auto-MDIX might connect
	- Try turning it on
- Locate reversal location
	- Often at a punchdown
	- Check your patch panel
### Dirty optical cables
- Light needs to be seen
	- Fiber connectors must be clean
	- Always use your dust caps
- Dirty connectors will inhibit or prevent communication
	- Attenuation can prevent data transfer
- Clean thoroughly before using
	- Just before installation
## Hardware Tools
### Cable Crimper
- Pinch the connector onto the wire
- Final step of a cable installation
- Metal prongs push through insulation
### Punch-down Tool
- Forces wire into a wiring block
- Trims the wires and breaks the insulation
### Tone Generator
- Puts an analog sound on the wire
- Inductive probe doesn't need to touch the copper
- used with a toner probe to accurately identify the location of a cable pair or conductor within a wiring bundle, cross connection point or at the remote end.
### Loopback plug
- Useful for testing physical ports
- Serial, Ethernet, T1, fiber
- These are not crossover cables
### TDR / OTDR
- (Optical) Time Domain Reflectometer
- Estimate fiber lengths, measure signal loss, determine light reflection, create wire maps
- May require additional training
- Certify the performance of new fiber optics links and detect problems with existing fiber links
- Identify if a fiber cable is broken and provide an approximate location for the break in meters or feet.
- TDR is used for finding breaks in copper network cables and OTDR is used for fiber-optic network cables
### Multimeter
- AC/DC voltages
- Continuity, wire mapping
- Measuring instrument that can measure the voltage, resistance and amperage of a cable or conduit
### Light meter
- Send a light from one side
- Measure the light power on the other
- Optical Power Meter
- used to measure the power in an optical signal over a fiber optic cable
- Used to test if the cable is broken, but would not be able to determine where the break in the cable is
### Spectrum analyzer
- View the frequency spectrum
- Identify frequency conflicts
### Cable tester
- Continuity testing
- Identify missing pins, crossed wires
- Not used for advanced testing
### Taps and port mirrors
- Intercept network traffic
- Physical active or passive taps
- Port mirror from a switch
### Fusion splicer
- Join two fiber ends together
- Add connectors
- Repair fiber using heat
- Splicing together multiple fiber optic cables after a break
