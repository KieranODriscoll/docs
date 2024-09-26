# 2.3 - Race Conditions
## Race Condition
- A programming conundrum
	- Sometimes, things happen at the same time
	- This can be bad if you've not planned for it
- Time-of-check to time-of-use attack (TOCTOU)
	- Check the system
	- When do you use the results of your last check?
	- Something might happen between the check and the use
### Race condition example
- Two back accounts with $100
	- User 1 and User 2 transfer $50 from Account A to Account B
	- Expected outcome: Account A has $50, Account B has $150 (or A has $0 and B has $200)
- What if you don't perform proper validation?
	- User 1 and user 2 check the account balances ($100 in each account)
	- User 1 transfer $50 from Account A (now at $50) to Account B (now at $150)
	- At about the same time, user 2 transfers $50 from Account A (still has $100, right?, so now at $50) to Account B (now at $200)
	- Outcome: Account A has $50, Account B has $200
## Race conditions can cause big problems
- January 2024 - Mars rover "Spirit"
	- Reboot when a problem is identified
	- Problem is with the file system, so reboot because of the file system problem
	- Reboot loop was the result
- Pwn2Own Vancouver 2023 - Tesla Model 3
	- TOCTOU attacks against the Tesla infotainment using Bluetooth
	- Elevated privileges to root
	- Earn $100,000 US prize and they kept the Tesla
![Pasted_image_20240908120351](//assets/Pasted_image_20240908120351.webp)
