# 3.1a - Cloud Infrastructure
## Cloud responsibility matrix
- IaaS, PaaS, SaaS, etc
	- Who is responsible for security?
- Security should be well documented
	- Most cloud providers provide a matrix of responsibilities
	- Everyone knows up front
- There responsibilities can vary
	- Different cloud providers
	- Contractual agreements
	- Responsibility matrix example
## Hybrid considerations
- Hybrid cloud
	- More than one public or private cloud
	- This adds additional complexity
- Network protection mismatches
	- Authentication across platforms
	- Firewall configurations
	- Server settings
- Different security monitoring
	- Logs are diverse and cloud-specific
- Data leakage
	- Data is shared across the public Internet
## Third-party vendors in the cloud
- You, the cloud provider, and third-parties
	- Infrastructure technologies
	- Cloud-based appliances
- Ongoing vendor risk assessments
	- Part of an overall vendor risk management policy
- Include third-party impact for incident response
	- Everyone is part of the process
- Constant monitoring
	- Watch for changes and unusual activity
## Infrastructure as code
- Describe an infrastructure
	- Define servers, network, and applications as code
- Modify the infrastructure and create versions
	- The same way you version application code
- Use the description (code) to build other application instances
	- Build it the same way every time based on the code
- An important concept for cloud computing
	- Build a perfect version every time
## Serverless architecture
- Function as a Service (FaaS)
	- Apps are separated into autonomous functions
	- Remove the operating system from the equation
- Develop still creates the server-side logic
	- Runs in a stateless compute container
- May be even triggered and ephemeral
	- May only run for one event
- Managed by a third-party
	- All OS security concerns are at the third party
## Microservices and APIs
- Monolithic applications
	- One big application that does everything
- Application contains all decision making processes
	- User interface, business logic, data input and output
- Code challenges
	- Large codebase, change control challenges
- APIs - Application Programming Interfaces
- API is the "glue" for the microservices
	- Work together to act as an application
- Scalable - Scale just the microservices you need
- Resilient - Outages are contained
- Security and compliance - Containment is built-in
![](Pasted%20image%2020240913134401.png)