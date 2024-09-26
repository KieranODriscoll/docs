# 4.5c - Operating System Security
## Active Directory
- A database of everything on the network
	- Computers, user accounts, file shares, printers, groups and more
	- Primarily Windows-based
- Manage authentication
	- Users login using their AD credentials
- Centralized access control
	- Determine which users can access resources
- Commonly used by the help desk
	- Reset passwords, add and remove accounts
## Group Policy
- Manage the computers or users with Group Policies
	- Local and Domain policies
	- Group Policy Management Editor
- A central console
	- Login scripts
	- Network configurations (QoS)
	- Security parameters
- Comprehensive control
	- Hundreds of configuration options
## Security-Enhanced Linux (SELinux)
- Security patches for the Linux kernel
	- Adds mandatory access control (MAC) to Linux
	- Linux traditionally uses
	- Discretionary Access Control (DAC)
- Limits application access
	- Least privilege
	- A potential breach will have limited scope
- Open source
	- Already included as an option with many Linux distributions