# 4.1b - Hardening Targets
## Hardening targets
- No system is secure with the default configurations
	- You need some guidelines to keep everything safe
- Hardening guides are specific to the software or platform
	- Get feedback from the manufacturer or Internet interest group
	- They'll have the best deatils
- Other general-purpose guides are available online
## Mobile devices
- Always-connected mobile technologies
	- Phones, tablets, etc
	- Hardening checklists are available from manufacturers
- Updates are critical
	- Bug fixes and security patches
	- Prevent any known vulnerabilities
- Segmentation can protect data
	- Company and user data are separated
- Control with an MDM - Mobile Device Manager
## Workstations
- User desktops and laptops - Windows, macOS, Linux, etc
- Constant monitoring and updates
	- Operating systems, applications, firmware, etc
- Automate the monthly patches
	- There's likely an existing process
- Connect to a policy management system
	- Active Directory group policy
- Remove unnecessary software - Limit the threats
## Network infrastructure devices
- Switches, routers, etc
	- You never seem them, but they're always there
- Purpose-built devices
	- Embedded OS, limited OS access
- Configure authentication
	- Don't use the defaults
- Check with the manufacturer
	- Security updates
	- Not usually updated frequently
	- Updates are usually important
## Cloud infrastructure
- Secure the cloud management workstation
	- The keys to the kingdom
- Least privilege
	- All services, network settings, application rights and permissions
- Configure Endpoint Detection and Response (EDR)
	- All devices accessing the cloud should be secure
- Always have backups
	- Cloud to Cloud (C2C)
## Servers
- Many and varied
	- Windows, Linux, iOS, Android
- Updates
	- Operating system updates/service packs, security patches
- User accounts
	- Minimum password lengths and complexity
	- Account limitations
- Network access and security
	- Limit network access
- Monitor and secure
	- Anti-virus, anti-malware
## SCADA / ICS
- Supervisory Control and Data Acquisition System
	- Large-scale, multi-site Industrial Control Systems (ICS)
- PC manages equipment
	- Power generation, refining, manufacturing equipment
	- Facilities, industrial, energy, logistics
- Distributed control systems
	- Real-time information
	- System control
- Requires extensive segmentation
	- No access from the outside
## Embedded systems
- Hardware and software designed for a specific function
	- Or to operate as part of a larger system
- Can be difficult to upgrade
- Correct vulnerabilities
	- Security patches remove potential threats
- Segment and firewall
	- Prevent access from unauthorized users
## RTOS (Real-Time Operating System)
- An operating system with a deterministic processing schedule
	- No time to wait for other processes
	- Industrial equipment, automobiles, military environments
- Isolate the system
	- Prevent access from other areas
- Run with the minimum services
	- Prevent the potential for exploit
- Use secure communication
	- Protect with a host-based firewall
- Needs to be checked for security including any default passwords
## IoT Devices
- Heating and cooling, lighting, home automation, wearable technology, etc
- Weak defaults
	- IoT manufacturers are not security professionals
	- Change those passwords
- Deploy updates quickly
	- Can be a significant security concern
- Segmentation - Put IoT devices on their own VLAN