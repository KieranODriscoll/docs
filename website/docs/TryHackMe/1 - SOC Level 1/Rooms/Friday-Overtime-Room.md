# Friday Overtime Room
## Introduction
- A ticket is logged on the CTI platform, malware was sent over and requires analysis
- Perform analysis on the sample and answer the flag questions

## Obtain SHA1 hash
- The second flag asks to determine the SHA1 hash of a file inside the samples.zip
- So we need to not only download, but extract and then run sha1sum on the desired .dll file
- Inside the email on DocIntel, we have a password for the zip file: "Panda321!"
- Extract the files from the zip and then calculate the SHA1 hash
![Pasted_image_20241104195535](//assets/Pasted_image_20241104195535.webp)
## Malware Framework
- Next step is to determine the malware framework that utilizes these DLLs as add-on modules
- Searching the pRsm.dll, leads to an article [Evasive Panda APT](https://www.welivesecurity.com/2023/04/26/evasive-panda-apt-group-malware-updates-popular-chinese-software/)
- Found in the article is the custom framework known as MgBot which is the answer to the 3rd flag
## MITRE ATT&CK Technique
- This one was a little tricky. I originally searched pRsm.dll and followed links to Mitre techniques, which leads to T1055, Dynamic-link Library Injection, which I figured would be the answer, but that is not the case.
- You can find MgBot on ATT&CK as well, which holds the answer, but not very clearly. [MgBot](https://attack.mitre.org/software/S1146/)
	- This lists all the techniques used, but none of them specifically call out pRsm.dll
- The article previously holds the answer, near the bottom of the article, it provides a detailed analysis of its dll files and what they do. Which we can link back to the MITRE ATT&CK technique
![Pasted_image_20241104200148](//assets/Pasted_image_20241104200148.webp)
- Capturing input and output audio streams corresponds with **T1123**
## Defang download location & C2 Location
- Next step is to find the download location first seen in 2020-11-02
- The Evasive Panda article has a technical analysis which provides our answer
![Pasted_image_20241104200340](//assets/Pasted_image_20241104200340.webp)
- The defanged version is: 
	- `hxxp[://]update[.]browser[.]qq[.]com/qmbs/QQ/QQUrlMgr_QQ88_4296[.]exe`
- Near the bottom of the article it goes over IOCs
	- One specific section is Network which provides C2 Server IPs
- The defanged version is:
	- `122[.]10[.]90[.]12`
## SHA1 hash of the spyagent family spyware
- Last question asks to find the SHA1 hash of the spyagent family spyware hosted on the same IP as above.
- Plugging the IP address into [Virustotal](https://www.virustotal.com/gui/ip-address/122.10.90.12/relations), we can see under relations a corresponding Android type
![Pasted_image_20241104200831](//assets/Pasted_image_20241104200831.webp)
- Following the link and looking under details we can find the SHA1 hash and answer the question
![Pasted_image_20241104200904](//assets/Pasted_image_20241104200904.webp)
## Conclusion
- That concludes the room, not bad for an easy level difficult and gives a good intro into the analysis of samples.
