# 1.3 - Yara

## About Yara
- Pattern matching swiss knife for malware researchers (and everyone else)
- Can identify information based on both binary and textual patterns, such as hexadecimal and strings contained within a file
- Rules are used to label these patterns
- Example
	- To determine if a file is malicious or not, based upon the features - or patterns - it presents
	- Strings are a fundamental concept of programming.
	- Applications use strings to store data such as text
	- Malware use of Strings
		- ![](assets/Pasted%20image%2020241104121329.png)
## Introduction to Yara Rules
- Every yara command requires 2 arguments to be valid
	- The rule file
	- Name of the file, directory or process ID to use the rule for
- Example of a rule
 ![](assets/Pasted%20image%2020241104122419.png)
	- Contains both a name and a condition, so this rule is valid. This rule will tell us if the file exists or not. Not very helpful
## Expanding on Yara Rules
- Other conditions:
	- Meta
		- Reserved for descriptive information by the author of the rule
		- Can use desc, to summarize what your rule checks for. Anything within this section does not influence the rule itself.
	- Strings
		- Search for specific text or hexadecimal
		- Keyword Strings where the string that we want to search is stored within a variable
		- ![](assets/Pasted%20image%2020241104124346.png)
		- We would then need a condition to make the rule valid, we would use the variable's name
		- ![](assets/Pasted%20image%2020241104124601.png)
		- Now what if we wanted to use multiple strings? We can use condition "any of them" to search for all the strings listed
		- ![](assets/Pasted%20image%2020241104124802.png)
	- Conditions
		- Already used true and any of them conditions.
		- Can also use operators: {'<='}, {'>='}, {'!='}
		- Example:
		![](assets/Pasted%20image%2020241104124855.png)
			- This will look for "Hello World!" and only match if there are less than or equal to 10 occurrences
		- Other Keywords
			- and
			- not
			- or
		- Combine multiple conditions with and, not, or
		![](assets/Pasted%20image%2020241104125052.png)
