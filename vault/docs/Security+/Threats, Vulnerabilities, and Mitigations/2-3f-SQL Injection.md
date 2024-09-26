# 2.3f - SQL Injection
## Code Injection
- Adding your own information into a data stream
- Enabled because of bad programming
	- The application should properly handle input and output
- So many different data types
	- HTML, SQL, XML. LDAP, etc
## SQL Injection
- SQL - Structured Query Language
	- The most common relational database management system language
- SQL Injection (SQLi)
	- Put your own SQL requests into an existing application
	- Your application shouldn't allow this
	- Stored procedures protect against SQL injection attacks because they prevent user-supplied from being interpreted as code
- Can often by executed in a web browser
	- Inject in a form or field
![](Pasted%20image%2020240908122526.png)