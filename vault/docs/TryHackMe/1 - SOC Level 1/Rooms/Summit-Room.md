# Summit (Room)
## Objective
- PicoSecure is conducting a threat simulation and detection engineering engagement to bolster malware detection capabilities
- Configure security tools to detect and prevent malware from executing
- Follow the Pyramid of Pain's ascending priority of indicators to increase cost of operations for adversary
## Sample 1
- ![](assets/Pasted%20image%2020241011094734.png)
- After scanning the first sample, we are given a page of information about the sample. If we start at the first level of the pyramid which is hashes, we can use the hashes to detect the first sample. For reference: [Pyramid of Pain#Hash Values (Trivial)](/docs/TryHackMe/1%20-%20SOC%20Level%201/1-2-Pyramid-of-Pain.md#Hash%20Values%20(Trivial))
- Moving to the Detect Hashes page, we can add the 3 hashes to detect the sample, in this case the MD5 hash was added to the detection list and a flag was received in the mail.
	- ![](assets/Pasted%20image%2020241011095056.png)
## Sample2
- Moving on to sample2, since hash files are a very high confidence indicator that something is malware, you can be sure it is malware if you see the hash again. However, this makes it easy to bypass this detection mechanism since hashes are easily changed. For sample2, a different method of detection is required
- The next level of the pyramid is IP Addresses, so we will use that for detection this time. After analysis we can see there is some network activity. For Reference [Pyramid of Pain#IP Addresses (Easy)](/docs/TryHackMe/1%20-%20SOC%20Level%201/1-2-Pyramid-of-Pain.md#IP%20Addresses%20(Easy))
	- ![](assets/Pasted%20image%2020241011095524.png)
- Blocking the Intrabuzz Hosting Limited should be enough to stop this malware
- Create a firewall rule to block this IP address, and receive the flag in the mail
	- ![](assets/Pasted%20image%2020241011100215.png)
	- Egress is the proper rule to implement, preventing any communication leaving the network to the C2 server
## Sample 3
- Moving on to Sample 3, we can no longer use IP address to prevent the malware, so we will work our way further up the pyramid. The next level is Domain Names, for reference [Pyramid of Pain#Domain Name (Simple)](/docs/TryHackMe/1%20-%20SOC%20Level%201/1-2-Pyramid-of-Pain.md#Domain%20Name%20(Simple))
- We can see more network activity after analyzing the malware and we can see one malicious domain name, so lets block it
	- ![](assets/Pasted%20image%2020241011100559.png)
- Add the domain name and deny it, don't need the subdomain in the rule
	- ![](assets/Pasted%20image%2020241011100716.png)
## Sample 4
- The next level in the pyramid is Host artifacts so we will use that as the detection method. For reference [Pyramid of Pain#Host Artifacts (Annoying)](docs/TryHackMe/1%20-%20SOC%20Level%201/1-2-Pyramid-of-Pain.md#Host%20Artifacts%20(Annoying))
- Host Artifacts can be things like Registry Values and after the analysis we can see registry activity. So lets attempt to block based on these artifacts
	- ![](assets/Pasted%20image%2020241011101215.png)
- We also see some behaviour analysis which may help as well
	- ![](assets/Pasted%20image%2020241011101308.png)
- Starting with Registry activity, lets create a rule to detect the change to the DisableRealtimeMonitoring using the Rule creator
	- ![](assets/Pasted%20image%2020241011101644.png)
	- ![](assets/Pasted%20image%2020241011101653.png)
- This looks to have worked, as we have received mail for Sphinx
## Sample 5
- Moving on to sample 5, our old tricks will not work anymore so we must move up the pyramid of pain which brings us to Network Artifacts. For reference [Pyramid of Pain#Network Artifacts (Annoying)](docs/TryHackMe/1%20-%20SOC%20Level%201/1-2-Pyramid-of-Pain.md#Network%20Artifacts%20(Annoying))
- This stage revolves around finding user-agent strings, c2 information, URI patterns
- Based on the network log we received, we can see a consistent 97 byte request happening every 30 minutes
	- ![](assets/Pasted%20image%2020241011103504.png)
- So we will wanted to create a Network Connections rule using Sysmon Event Logs. It needs to be vague enough to capture any changes in port or IP address but specific to the pattern. 97 bytes and 30 minute frequency
	- ![](assets/Pasted%20image%2020241011103641.png)
	- This rule above looks to have worked and received mail from Sphinx
## Sample 6 - Final Sample
- Moving back up the pyramid for the final sample, we will have to look at detecting tools (maybe TTPs depending since there are 2 levels left). For reference, [Pyramid of Pain#Tools (Challenging)](docs/TryHackMe/1%20-%20SOC%20Level%201/1-2-Pyramid-of-Pain.md#Tools%20(Challenging))
- We have received a command log from Sphinx this time
	- ![](assets/Pasted%20image%2020241011103943.png)
- Reading the email further, it states we will have to do more than just tool detection, so it seems to be focused on the last level of the pyramid. For reference [Pyramid of Pain#TTPs (Tough)](docs/TryHackMe/1%20-%20SOC%20Level%201/1-2-Pyramid-of-Pain.md#TTPs%20(Tough))
- This involves the entire MITRE ATT&CK Matrix, all steps they take to achieve their goals.
- We can see above a pattern in the path they use and the name of the log file to attempt to exfiltrate. Lets try blocking this
	- ![](assets/Pasted%20image%2020241011104333.png)
	- This looks to have been successful, Sphinx has given up.