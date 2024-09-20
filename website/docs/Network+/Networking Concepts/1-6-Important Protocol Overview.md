# 1.6 - Important Protocol Overview
## DHCP Overview
### DHCP
- IPv4 address configuration used to be manual
	- IP address, subnet mask, gateway, DNS servers, NTP servers, etc
- Initially released in 1997
- Provides automatic address / IP configuration for almost all devices
![Pasted_image_20240606133217](//assets/Pasted_image_20240606133217.webp)
#### Managing DHCP in the enterprise
- Limited communication range
	- Uses the IPv4 broadcast domain
	- Stops at a router
- Multiple servers needed for redundancy
	- Across different locations
- Scalability
	- May not want or need to manage
	- DHCP servers at every remote location
- Need a helper
	- Send DHCP request across broadcast domains
### Configuring DHCP
#### Scope properties
- IP address range (and excluded addresses)
- Exclusion Range
	- Is a range of IP addresses that are defined within a DHCP scope
	- Are excluded from being leased to the clients
- Reservation
	- Is used to assign the same IP address to the client
	- Is tied to the client's MAC address
	- Prevents the same IP address to be assigned to other hosts
- Subnet mask
- Lease durations
	- Time that the clients are assigned an IP address
- Available Leases
	- Is the number of leases available in a scope
- Other scope options
	- DNS server, default gateway, WINS server
	- Set of additional information that is assigned to the client by a DHCP server with an IP address
		- 003 Router List - list of IP addresses as the default gateway
		- 005 Name Servers - List of available DNS servers
		- 015 DNS Domain Name: The fully qualified domain name suffix for a client
		- 042 NTP Servers: List of NTP servers
#### DHCP pools
- Grouping of IP addresses
	- Each subnet has its own scope
	- 192.168.1.0/24, 192.168.2.0/24 etc
- A scope is generally a single contiguous pool of IP addresses
	- DHCP exceptions can be made inside of the scope
#### DHCP address assignment
- Dynamic assignment
	- DHCP server has a big pool of addresses to give out
	- Addresses are reclaimed after a lease period
- Automatic allocation
	- Similar to dynamic allocation
	- DHCP server keeps a list of past assignments
	- You'll always get the same IP address
- Static assignment
	- Administratively configured table of MAC addresses
	- Each MAC address has a matching IP address
	- Other names - Static DHCP assignment, static DHCP, address reservation, IP reservation
#### DHCP leases
- Leasing your address
	- Only temporary
	- Can seem permanent
- Allocation
	- Assigned a lease time by the DHCP server
	- Administratively configured
- Reallocation
	- Reboot your computer
	- Confirm the lease
- Workstation can also manually release the IP address
	- Moving to another subnet
#### DHCP renewal
- T1 timer
	- Check in with the lending DHCP to renew the IP address
	- 50% of the lease time (by default)
- T2 timer
	- If the original DHCP server is down try rebinding with any DHCP server
	- 87.5% of the lease time (7/8ths)
- DHCP Timers
![Pasted_image_20240606134408](//assets/Pasted_image_20240606134408.webp)
#### DHCP Relay
- Forwards the DHCP packets between the client and DHCP server
- Is required when a client and DHCP server is not on the same network
	- If not configured, router will discard the broadcast packet sent by the client
![Pasted_image_20240619135405](//assets/Pasted_image_20240619135405.webp)
- To provide IP addresses to the systems on different VLANs, you need to configure the DHCP relay on routers configured on each VLAN. By default, the routers discard the broadcast messages. On the other hand, a DHCP clients sends a broadcast message to the DHCP server to obtain an IP address. When a router receives a broadcast message, it will simply discard it.
- Would need a DHCP server on each VLAN to handle this. OR you can configure a DHCP relay agent on the routers responsible for forwarding broadcast messages to the DHCP server as a unicast message
#### DHCP IP Helper
- DHCP IP Helper addresses enable a single DHCP server to provide DHCP IP addresses to every PC on the network, regardless of whether they are on the same broadcast domain as the DHCP server or not
- Configured on a routed interface such as a VLAN interface or a routers Ethernet interface that allows that specific device to act as a "middle man" which forwards DHCP requests it receives on the interface to the DHCP server

## Overview of DNS
### Domain Name System
- Translates human-readable names into computer-readable IP addresses
- Hierachical
- Distributed database
	- Many DNS servers
	- 13 root server clusters (1000+ actual servers)
	- Hundreds of generic to-level domains (gTLDs)
	- Over 275 country code top-level domains (ccTLDs)
#### The DNS hierarchy
![Pasted_image_20240619140323](//assets/Pasted_image_20240619140323.webp)
- Follows a tree-like hierarchy
- Top is the root zone, which is responsible for answering the queries for the records that they have stored
- Below root zone, a Top Level Domain (TLD) server receives querier from the DNS server in the root zone.
- Below TLD servers are the DNS servers that hold the domain names
#### Internal vs External DNS
##### Internal DNS
- Managed on internal servers
- Configured and maintained by local team
- Contains DNS information about internal devices
- DNS service on Windows Server
##### External DNS
- Often managed by a third-party
- Used as authoritative-only to handle public queries
- Does not have internal device information
- Google DNS, Quad9
#### Authoritative Name Servers
- Hold the authority for a zone
- Are queried by the recursive name servers for DNS records
![Pasted_image_20240619140909](//assets/Pasted_image_20240619140909.webp)
- Other DNS servers send the queriers to the authoritative DNS servers for name resolution
- DNS servers are NEVER authoritative for the data it caches, it is only authoritative for the information it holds
#### Lookups
- Forward lookup
	- Provide the DNS server with a Fully Qualified Domain Name (FQDN)
	- DNS server provides an IP address
- Reverse DNS
	- Provide the DNS server with an IP address
	- The DNS server provides an FQDN
#### Time To Live (TTL)
- Is a field in the DNS reply
- Defines the duration for which the client should store the reply
- Reply contains a TTL field that defines the lifetime duration of the query that will be cached at the client end.
- DNS Caching
	- Temporary storage that contains the old DNS lookups
		- Can be OS or Web browser
#### Recursive and Iterative DNS queries
- Many ways to get what you need
##### Recursive DNS Query
- Delegate the lookup to a DNS server
	- The DNS server does the work and reports back
	- Large DNS cache provides a speed advantage
![Pasted_image_20240606140353](//assets/Pasted_image_20240606140353.webp)
- DNS client queriers the DNS server
- DNS server responds with an answer or can query other DNS servers
- Responds with a valid address or a message indicating that the address cannot be found
##### Iterative DNS Query
- Do all the queries yourself
- Your DNS cache is specific to you
![Pasted_image_20240606140440](//assets/Pasted_image_20240606140440.webp)
- DNS client queries the DNS server
- DNS server responds with an answer
- If not, it queries the highest-level DNS server and is referred to the authoritative DNS server
- Returns a referral/address of another DNS server which might have the required information
- May not return what you are looking for
### DNS Records Types
![Pasted_image_20240619140131](//assets/Pasted_image_20240619140131.webp)
#### Resource Records (RR)
- The database records of domain name services
- Over 30 record types - IP addresses, certificates, host alias name, etc
#### Start of Authority (SOA)
- Describes the DNS zone details
- Stores administrative information about a domain or zone
- Structure
	- In SOA (internet zone, start of authority) with name of zone
	- Serial number
	- Refresh, retry, and expiry timeframes
	- Caching duration/TTL (time to live)
![Pasted_image_20240606140928](//assets/Pasted_image_20240606140928.webp)
#### Address Records (A) (AAAA)
- Defines the IP address of a host
	- This is the most popular query
- A records are for IPv4 addresses
	- Modify the A record to change the host name to IP address resolution
- AAAA records are for IPv6 addresses
	- The same DNS server, different records
![Pasted_image_20240606141138](//assets/Pasted_image_20240606141138.webp)
#### Canonical name records (CNAME)
- A name is an alias of another, canonical name
	- One physical server, multiple services
![Pasted_image_20240606141213](//assets/Pasted_image_20240606141213.webp)
#### Service records (SRV)
- Find a specific service
- Where is the Windows Domain Controller? Where is the instant messaging server?
![Pasted_image_20240606141255](//assets/Pasted_image_20240606141255.webp)
#### Mail exchanger record (MX)
- Determines the host name for the mail server - this isn't an IP address; it's a name
![Pasted_image_20240606141333](//assets/Pasted_image_20240606141333.webp)
#### Name server records (NS)
- List the name servers for a domain - NS records point to the name of the server
![Pasted_image_20240606141425](//assets/Pasted_image_20240606141425.webp)
#### Pointer record (PTR)
- The reverse of an A or AAAA record
	- Added to a reverse map zone file
![Pasted_image_20240606141459](//assets/Pasted_image_20240606141459.webp)
#### Text records (TXT)
- Human-readable text information
- Useful public information
##### SPF protocol (Sender Policy Framework)
- Prevent mail spoofing
- Mail servers check that incoming mail really did come from an authorized host
![Pasted_image_20240606141828](//assets/Pasted_image_20240606141828.webp)
##### DKIM (Domain Keys Identified Mail)
- Digitally sign your outgoing mail
- Validate by the mail server, not usually seen by the end user
- Put your public key in the DKIM TXT record
![Pasted_image_20240606141836](//assets/Pasted_image_20240606141836.webp)
### Zone Transfers
- Replicate a DNS database
	- The primary DNS server has the primary copy of the zone information
- Synchronize to a secondary server
	- Provide redundancy
- Triggered by referencing the serial number
	- if the serial number increases, there must have been a change
- Full zone transfer can be a security risk
-  Replicating the zone to the secondary DNS server:
	- Redundancy
	- Load balancing
	- Can be incremental or full depending on the changes required to be replicated
![Pasted_image_20240619140453](//assets/Pasted_image_20240619140453.webp)
- Core intent of the zone transfer is to replicate the zone file from one server to another server
- Primary DNS server never initiates the zone transfer, the secondary DNS server always owns the responsibility of zone transfer from the primary DNS server.
### Split-horizon or Split-view DNS
- An implementation in which separate DNS servers are provided for security and privacy management for internal and external networks.
- Provides a security and privacy management mechanism by logical or physical separation of DNS information for network-internal access and access from insecure, public networks
- 2 sets of DNS information and results are provided based on the source address of the requester

## An Overview of NTP
- Which devices are clients, servers, and client/servers
### NTP Clients and Servers
#### NTP Server
- Respond to time requests from NTP clients
- Does not modify their own time
#### NTP Client
- Requests time updates from NTP server
#### NTP Client/Server
- Requests time updates from an NTP server
- Responds to time requests from other NTP clients
#### NTP stratum layers
- Indicates the accurate time source
- Is a hierarchy of stratum levels
- Lower the number the more accurate time is
- Starts with 0 to 15, level 16 indicates that the device is unsynchronized
- Some clocks are better than others
	- Your distance from the original reference clock is a stratum
- Stratum 0
	- Atomic clock, GPS clock
	- Very accurate
- Stratum 1
	- Synchronized to stratum 0 servers
	- Primary time servers
- Stratum 2
	- Sync'd to stratum 1 servers
![Pasted_image_20240619151922](//assets/Pasted_image_20240619151922.webp)
- 
### Configuring NTP
#### NTP Client
- Specify the NTP server address (IP or hostname)
- Use multiple NTP servers (if available) for redundancy
#### NTP Server
- You need at least one clock source
- Specify the stratum level of the clock
- If there's a choice, the lower stratum level wins
- Are used to either synchronize time at the lower stratum levels or with the network devices
- Can be a specialized piece of hardware
- Are used by the networking devices to synchronized clocks
- Synchronize with the atomic clock
- Can be internal or external to a network


