# Show
## show diagnostic
- display details about the hardware and software on each node in a networked device
## show config
- displays the device's current configuration, including things like if DHCP snooping in enabled
## show route
- display the current state of the routing table for a given network device. This would be used to determine the routing protocol used
## show interface
- displays the statistics for a given network interface
# nbtstat
- NetBIOS stores a local cached named table in the LMHOSTS file on each client. If the entry in the client file is pointing to the wrong IP, this could cause the connectivity issues
## -R
- purges and reloads the cached name table from the LMHOST file on their Windows workstation

# netstat
## -a
- displays all active TCP connections and the TCP/UDP ports on which the computer is listening
## -r
- Displays the contents of a routing table
## -b
- displays the names of applications and executable file components that are accessing the network
# nslookup
- used to query DNS to obtain information about host addresses, mail exchanges, nameservers and related information
# ipconfig
- used to display the current TCP/IP network configuration and refresh the DHCP and DNS settings on a given host.
## /release
- releases the IP address of the workstation executing the command
## /renew
- Dynamically assign another IP address of the workstation executing the command
- Would renew an existing DHCP lease if the workstation already has one, would not request a new IP address
## /all
- used to display the assigned IP addresses
- Also displays physical address of a network interface card
# route
- used to create, view or modify manual entries in the network routing tables of a computer or server
# pathping
- Command-line utility in MS Windows that combiners the features of ping and tracert
