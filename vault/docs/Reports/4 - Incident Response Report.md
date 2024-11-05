# Incident Response Report
## Incident Details

On February 24, 2024, at 2:28pm, a large amount of traffic towards the network occurred and originated from a single IP address. Upon further analysis, it appears the IP address scanned the network to see which hosts were alive and then further scanned each alive host for vulnerabilities. These scans affected the following IP addresses on the network: 10.0.69.5, 10.0.69.6, 10.0.69.8, 10.0.69.10, 10.0.69.11, 10.0.69.12. This traffic is confirmed by wireshark and for some agents confirmed on Wazuh. While this is a normal occurrence and sometimes done from some time of automation, more attention was paid to the network at this time. At this time, no incident was required to be raised.

Later in the day, around 3:25pm, it became apparent that someone had attempted to gain unauthorized access to several system and succeeded. An incident was raised and classified as unauthorized access and a data breach. The affected systems based on analysis of wireshark logs showed that metasploitable (10.69.0.10), Ubuntu 22.04 (10.0.69.8) and Bee box (10.0.69.11) systems were compromised. It appears the attacker had access to the network for approximately 15 minutes before access to the affected machines were cut off.

## Impact Analysis

### 10.0.69.8 – Ubuntu

Based on analysis of the Wireshark logs found on the Ubuntu system, it can be concluded that the attacker gained access by uploading a php reverse shell. The attacker then navigated around the system and exfiltrated the passwd file found in the /etc/ folder. Nothing else was stolen and it appears the attacker did not spend much time on this system. Impact from this system is minimal but all user accounts associated with the system have been compromised and have the potential to be used in subsequent attacks. The logs regarding the scanning, uploading of the payload and enumeration of the system can be found in Appendix 1.

### 10.0.69.10 – Metasploitable

Wireshark was not running on the metasploitable system but a wazuh agent was set up. Based on the logs captured by Wazuh, a vulnerability scan was conducted against the system and subsequently a ProFTPD session was opened. Beyond that there is little in the way of logs to help give a sense of what occurred and what was stolen. Upon inspection of the systems file contents, it appears the hacker did not have enough time to clean up its assets and we can see that a c program was uploaded to the system with the name PwnKit.c. Further investigation reveals that this corresponds to a privilege escalation technique that affects the kernel version found on the system. It can be concluded that the attacker managed to gain root access to the system and all information should be considered compromised, including any passwords in cleartext or hashed on the system. See appendix 2 to see the Wazuh alert.

### 10.0.69.11 – BeeBox

Wireshark and Wazuh are not compatible with the Linux kernel on the BeeBox. But based on the kernel version and applications running on them that are similar to the Ubuntu and Metasploitable systems, it his highly probable that similar attacks were conducted against the BeeBox system. Further analysis of the files that remained on the system shows that files were uploaded through ProFTPD that resulted in reverse shell access for the attacker. It also shows that many attempts were made to escalated privileges and it is inconclusive if this was successful or not. It should be assumed that at least one attempt was successful in obtaining root access. It should be concluded that a full system breach occurred and any information on the system is compromised. See Appendix 3 for remnants of files from the attacker.

### Other

There is no evidence that any of the other systems were breached.

## Incident Response Actions

At 2:24pm when it was noticed that scanning was being done on the network, alert levels were raised but no formal incident was raised. Scanning is common against large companies and websites and does not indicate anything malicious instantly. However, the complacency in this thinking resulted into the progression to an incident. At 3:34pm, based on Wireshark logs, it was concluded that unauthorized access to the network had occurred. The first course of action was to determine the systems affected and isolate each from the network. This was achieved by applying firewall rules in PFSense to block any traffic originating from the affected systems as well as blocking any traffic destinated for the affected systems. This prevented an attacker from communicating with the affected systems as well as communicating with other systems in the network preventing any lateral movement. Next, as a more permanent solution that has no room for error, each of the affected machines were disconnected from the network until a formal diagnostic and eradication could take place. This involved the removal of any remnants left behind by the attacker and the terminating of processes used.

### Findings and Recommendations

It has been discovered that the three affected systems have many avenues an attacker can take to disrupt business operations, steal information or gain unauthorized access to the network. No one vulnerability can be given the status of root cause since they all can lead to the same outcome. The root cause is extremely out of date systems that have many publicly known vulnerabilities and exploits. It is recommended that these systems do not return to normal operations until they have been updated with the latest security updates and if that is not possible due to legacy software, a full risk analysis should be conducted, and alternative means of mitigation be implemented. Some examples of mitigation strategies could be keeping these systems for internal use only and not exposing them publicly (comes with its own risks if network access is obtained from another vulnerability) and/or the implementation of and Intrusion Prevention System (IPS) that will be configured to a strict setting and its signature databases updated regularly. Lastly, it is highly recommended that all passwords are updated and that they conform to a strict password policy including letters, numbers and symbols along with a reasonable required length to prevent password guessing and brute force attacks.

## Appendices

### Appendix 1 – Ubuntu Wireshark Logs
![](../../assets/Pasted%20image%2020241004164749.png)
![](../../assets/Pasted%20image%2020241004164800.png)
![](../../assets/Pasted%20image%2020241004164804.png)

### Appendix 2 - Metasploitable

![](../../assets/Pasted%20image%2020241004164816.png)
![](../../assets/Pasted%20image%2020241004164821.png)
## Appendix 3 – BeeBox
![](../../assets/Pasted%20image%2020241004164827.png)
