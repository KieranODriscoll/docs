# 4.6b - Access Controls
## Access Control
- Authorization
	- The process of ensuring only authorized rights are exercised
	- Policy enforcement
	- The process of determining rights
	- Policy definition
- Users receive rights based on
	- Access control models
	- Different business needs or mission requirements
## Least privilege
- Rights and permissions should be set to the bare minimum
	- You only get exactly what's needed to complete your objective
- All user accounts must be limited
	- Applications should run with minimal privileges
- Don't allow users to run with administrative privileges
	- Limits the scope of malicious behavior
## Mandatory Access Control (MAC)
- The operating system limits the operation on an object
	- Based on security clearance levels
- Every object gets a label
	- Confidential, secret, top secret, etc
- Labeling of objects uses predefined rules
	- The administrator decides who gets access to what security level
	- Users cannot change these settings
## Discretionary Access Control (DAC)
- Used in most operating systems
	- A familiar access control model
- You create a spreadsheet
	- As the owner, you control who has access
	- You can modify access at any time
- Very flexible access control
	- And very weak security
## Role-based Access Control (RBAC)
- You have a role in your organization
- Administrators provide access based on the role of the user
	- Rights are gained implicitly instead of explicitly
- In Windows, use Groups to provide role-based access control
	- You are in shipping and receiving, so you can use the shipping software
## Rule-based Access Control
- Users can have complex relationships to applications and data
	- Access may be based on many different criteria
- ABAC can consider many parameters
	- A "next generation" authorization model
	- Aware of context
- Combine and evaluate multiple parameters
	- Resource information, IP address, time-of-day, desired action, relationship to the data, etc
- Broad term that can encompass various access control mechanisims
## Time of Day Restrictions
- Almost all security devices include a time-of-day option
	- Restrict access during certain times or days of the week
	- Usually not the only access control
- Can be difficult to implement
	- Especially in a 24-hour environment
- Time-of-day restrictions
	- Training room network is inaccessible between midnight and 6am
## Attribute-based
- ABAC
- Access permissions are dynamically evaluated based on various user attributes, such as role, department, location and time of access.
- System combines these attributes to make access control decisions, allowing for more fine-grained and context-aware access control
