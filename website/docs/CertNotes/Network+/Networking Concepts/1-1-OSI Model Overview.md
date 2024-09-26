# 1.1 - OSI Model Overview
## OSI Model
- Way of traffic is moving between one section of the network to another
- Broad way to describe data movement
![Pasted_image_20240516144118](//assets/Pasted_image_20240516144118.webp)
- All People Seem To Need Data Processing

### Layer 1 - Physical Layer
- The physics of the network
- Signal, cabling, connectors
- This layer isn't about protocols
- "Physical layer problem"
	- Fix cabling, punch downs
	- Loopback tests, test/replace cables
- Real world: Cables, fiber, and the signal itself
- Does encoding and decoding
- Sends electrical impulses made up of 1s and 0s
![Pasted_image_20240516145107](//assets/Pasted_image_20240516145107.webp)
### Layer 2 - Data Link Layer
- The basic network "language"
- Data link control (DLC) Protocols
	- MAC (Media Access Control) address on ethernet
- The switching layer
- Real world: Frame, MAC Address, Extended Unique Identifier, Switch
- Responsible for communication between Network and Physical layer
- Nothing but layer-to-layer communication
- Creates frames and adds physical addresses
- Logical Link Control (LLC) sublayer - determines whether the communication is connection-oriented or connectionless
- MAC Sublayer - contains MAC Addresses, the physical addresses of NIC
### Layer 3 - Network layer
- Routing layer
- Internet Protocol (IP)
- Fragments frames to traverse different networks
- Real world: IP Addresses, Router, Packets
- Receive data from the transport layer and passes it over to the data-link layer
- Responsible for:
	- Address conversion
	- Source-to-destination delivery
	- Routing
- Works with the logical addressing, which can change
### Layer 4 - Transport layer
- "Post office" Layer
- TCP - transmission control protocol
- UDP - user datagram protocol
- Real world: TCP Segment, UDP datagram
- Responsible for:
	- End-to-end message delivery - message acknowledgment and traffic control
	- Error checking - packets arrive without duplication or corruption
- Utilizes port numbers to differentiate traffic and send it to the correct application
### Layer 5 - Session Layer
- Communication management between devices
- Real world: Control protocols, tunneling protocols
- Start, continue and end sessions
	- Establish, Maintain and terminate sessions
- Regulates the data exchange, acting as a moderator that determines who can transfer data and for how long
- Ensures all security concerns are met such as a login
- Manages dialog control: Simplex, Half-duplex, Full-duplex
- Some of the following protocols: NetBIOS, DNS, RPC and NFS
### Layer 6 - Presentation Layer
- Character encoding
- Application encryption
- Often combined with the application layer since it is so closely related to ability to use application
- Real world: Application encryption (SSL/TLS)
- Represents data in a uniform format to an application
- Translation layer
- Uses methods such as:
	- ASCII
	- XML
- Compresses data for transmission
### Layer 7 - Application Layer
- The layer we see
- HTTP, FTP, DNS, POP3
- Real world: your eyes

## Data Communication
- Moving data from one part of the network to another requires a Protocol Data Unit (PDU)
- Also known as transmission units, taking a little bit of data and transmitting across the network as a unit
- Ethernet operates on a frame of data
	- Doesn't care what is inside, encapsulates all the other data from the other layers
- IP operates on a packet of data
	- Inside is TCP or UDP, but doesn't care what else is inside
- TCP Segment, or UDP Datagram within the packet
![Pasted_image_20240516151502](//assets/Pasted_image_20240516151502.webp)
- Each layer has a header and payload, data frames often also have a trailer to show the end of the frame
- Header tells the rest of the data how it should be processed
- Ethernet Header
![Pasted_image_20240516152542](//assets/Pasted_image_20240516152542.webp)
	- Preamble - consists of 8 bytes (including 1 byte that is the start of frame delimiter). The other 7 bytes are used to establish synchronization between the sending and receiving devices. Alternating 1s and 0s
	- Destination address - MAC address of the recipient system
	- Source address - MAC address of the sender
	- Length: is a 2-byte long field that determines the length of the ethernet frame. Can hold between 0 and 65534, its length is restricted to 1500 due to limitations in ethernet
	- Payload: Contains the actual data, minimum length 46 bytes and a maximum length of 1500 bytes. If the length is shorter than 46, extra 0s are added to meet the minimum length
	- Frame Check Sequence (FCS) - uses cyclic redundancy check (CRC) to the field includes a mechanism to ensure that the frame is without any corruption. Contains a 32 bit hash value generated based on DA, SA, Length and data fields
- TCP Header contains important control information, TCP Flags
	- TCP Flags
		- Syn - Synchronize sequence numbers
		- PSH - push the data to the application without buffering
		- RST - reset the connection
		- FIN - last packet from the sender
![Pasted_image_20240516155941](//assets/Pasted_image_20240516155941.webp)
	- Source Port - 16-bit defining sender's port number
	- Destination Port - 16-bit defining receiver's port number
	- Sequence number - 32-bit defines the amount of data sent
	- Acknowledgement number - 32-bit field that is used by the receiver to request for the next TCP segment
	- Header-length - 4-bit defining header length
	- Reserved - 3-bit unused field that is always set to 0
	- Flags - 9 bit control bits used to establish and terminate connections
		- Nonce Sum (NS) - protects against malicious concealment of packets from a sender
		- Congestion Window Reduction (CWR) - acknowledgment that confirms that congestion-indication echoing is received
		- Explicit Congestion Notification Echo (ECE) - indicates congestion
		- Urgent (URG) - pointer that indicates that the data with this pointer needs to be given higher priority over other data
		- Acknowledgment (ACK)
		- Push (PSH) - mandates an application send data immediately without waiting for the entire TCP segment
		- Reset (RST)
		- Synchronize (SYN)
		- Finish (FIN)
	- Window size: 16-bit field that defines the number of bytes a receiver can receive
	- Checksum - 16-bit field that contains checksum to ensure TCP header is not corrupted or manipulated
	- Urgent pointer - is a 16-bit field that determines urgent data byte
	- Options - 0 to 320-bit to define the ending point for urgent data
- UDP Header
![Pasted_image_20240516160727](//assets/Pasted_image_20240516160727.webp)
- 
- IP Header
	- Maximum IP packet to transmit, but not fragment
	- Maximum Transmission Unit (MTU)
![Pasted_image_20240516161339](//assets/Pasted_image_20240516161339.webp)
	- Fragmentation slows things down
	- Losing a fragment loses an entire packet
	- Requires overhead along the path
	- Difficult to know the MTU all the way through the path
		- Automated methods are often inaccurate
![Pasted_image_20240516154210](//assets/Pasted_image_20240516154210.webp)
	- Some fields are static, some fields are dynamic and change over transmission
	- Required fields:
		- Service type -has the quality of service information
		- TTL - defines how long the packet is going to live
		- Source address - IP of the sending system
		- Destination address - IP of the receiving system
	- Other:
		- Version - IP Version, IPv4 or IPv6
		- Internet Header Length (IHL) - header length
		- Total length - total length of a packet that includes the header and data
		- Identification - used for unique fragment identification
		- Flag - Control flags for fragmentation
		- Fragment offset - defines where a specific fragment belongs
		- Protocol - upper-layer protocol used in the data portion
		- Header checksum - error detection
		- Options - various optional parameters
		- Padding - used for padding extra values to make it 32-bit
- Troubleshooting MTU
	- Usually set and configured once
	- Tunnel is a concern since a tunnel might have a smaller MTU
