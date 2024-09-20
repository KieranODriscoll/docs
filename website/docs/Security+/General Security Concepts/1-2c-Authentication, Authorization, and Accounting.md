# 1.2c - Authentication, Authorization and Accounting
## AAA Framework
### Identification
- This is who you claim to be
- Usually your username
### Authentication
- Prove you are who you say you are
- Password and other authentication factors
### Authorization
- Based on your identification and authentication, what access do you have?
### Accounting
- Resources used: Login time, data sent and received, logout time
## Authenticating Systems
- You have to manage many devices
	- Often devices that you'll never physically sdee
- A system can't type a password
	- And you may not want to store one
- How can you truly authenticate a device?
	- Put a digitally signed certificate on the device
- Other business processes rely on the certificate
	- Access to the VPN from authorized devices
	- Management software can validate the end device
## Certificate Authentication
 - An organization has a trusted Certificate Authority (CA)
	 - Most organizations maintain their own CAs
- The organization creates a certificate for a device
	- And digitally signs the certificate with the organization's CA
- The certificate can now be included on a device as an authentication factor
	- The CA's digital signature is used to validate the certificate
## Using an Authorization Model
![Pasted_image_20240905132545](//assets/Pasted_image_20240905132545.webp)
### Authorization models
- The user or device has now authenticated
	- To what do they now have access?
	- Time to apply an authorization model
- Users and services -> data and applications
	- Associating individual users to access rights does not scale
- Put an authorization model in the middle
	- Define by Roles, Organizations, Attributes, etc
### No authorization model
- A simple relationship
	- User -> Resource
- Some issues with this method
	- Difficult to understand why an authorization may exist
	- Does not scale
### Using an authorization model
- Add an abstraction
	- Reduce complexity
	- Create a clear relationship between the user and the resource
- Administration is streamlined
	- Easy to understand the authorizations
	- Support any number of users or resources
