# Penetration Test Report

## Executive Summary
### Objective

The purpose of this penetration test is to assist RandomCompany ( “the client” ) in the assessment of their network and evaluate areas that have vulnerabilities which could expose attackers to their network. The goal of the penetration test is to show weaknesses in the network and recommend solution so that the client can harden their infrastructure and mitigate risk associated with cyber incidents. It is not expected that all weaknesses will be cover as some may be missed. OD Company does not take responsibility for any attack that may occur from a missed weakness. The scope of the assessment is limited to the replicated production environment lab except for the PFSense router, Wazuh and Kali Linux. Any other system on the network will be subjected to a vulnerability assessment and penetration test.

### Test Methodology

The test methodology will follow the following phases: reconnaissance, scanning, vulnerability assessment exploitation, and potential privilege escalation. Reconnaissance is the gathering of information about the target system. Active reconnaissance will be the approach taken due to the nature of the lab environment. Scanning is the act of utilizing tools to identify open port, running services and their versions. This information is then used in the vulnerability assessment to determine if there are any vulnerabilities that can be used to gain access to the network. Once the vulnerability assessment is completed, exploitation occurs using the vulnerabilities identified in the previous phase. Once access has been established, if the access is not root/administrator level, enumerating the machine to determine if any privilege escalation methods exist.

### Key Findings

10.0.69.10 – Linux 3.13
- CVE-2015-3306 – ProFTPD 1.3.5, arbitrary file upload
- SA-CONTRIB-2016-039 – Drupal remote code execution
- CVE-2021-4034 – PwnKit Privilege escalation

When combined, any vulnerability above and the PwnKit Privilege escalation results in root level access for the attacker.

10.0.69.8 – bWAPP Ubuntu
- bWAPP web application is susceptible to directory and file traversal
- bWAPP web application is susceptible to unrestricted file upload

The above vulnerabilities allow an attacker to gain unauthorized access to files and potentially with unrestricted file upload, root access if a vulnerability is found for Ubuntu 22.04

10.0.69.11 – Linux 2.6.X
- CVE-2015-3306 – ProFTPD 1.3.5, arbitrary file upload
- SA-CONTRIB-2016-039 – Drupal remote code execution
- CVE-2010-2075 – UnrealIRDCD Backdoor
- CVE-2021-4034 – PwnKit Privilege escalation
- CVE-2023-32254 – Remote code execution or privilege escalation
- VNC - blank username, poor password configuration leading to root access
- Anonymous FTP account with write access

This system is easily compromised with many options for privilege escalation and root access.

### Recommendations

These recommendations apply to all three systems and any other system on the network even if not directly accessible. The client should keep up to date with security patches and kernel versions, various systems on the network are out of date and have known vulnerabilities with public exploits available. In addition, the web application hosted on two systems are susceptible to many vulnerabilities including some that give access to the system. It is recommended that either the web application undergoes a security assessment and ultimately updated or that the website be kept internally at a minimum. Keeping it internal reduces the likelihood of attack but does not stop someone from pivoting to it if within the network. Next, strong password policies should be implemented to prevent easy to guess passwords and the ability to brute force quickly. Lastly, ensure that even secure applications are configured properly. Misconfiguration of a secure application can still lead to vulnerabilities and exploits that an attacker can use to gain unauthorized access to the system and network.

## Introduction

### Background

The client has seen significant growth in its business and has focused on continuing that growth, however, this came at the expense of security. The client has asked that a penetration test be conducted so that they can obtain a thorough assessment of their network and what can be done to improve their security posture.

### Scope

The client has set up a replica of their production environment for the purpose of the penetration test. The penetration test is limited to this environment only and will focus on all systems within it except PFSense, Wazuh and Kali. Each system will undergo a full penetration test from scanning to vulnerability assessment to exploitation (if possible). Only some of the vulnerabilities will be exploited to show the impact of unpatched vulnerabilities.

## Test Methodology

### Approach

The approach to the penetration test will follow a black box style test. The network will be unknown besides PFSense, Wazuh and Kali. Other live systems on the network will be unknown to the tester and all information about a system will have to be gathered throughout the test. No other inside knowledge will be shared with the tester so that it can mimic an attacker’s approach into the network.

### Testing Phases

The following testing phases will be done on each system found on the network that is within scope: Reconnaissance, Vulnerability Assessment, Exploitation, Privilege escalation. Reconnaissance is the act of gathering information to help aid in attacking the target. Passive reconnaissance does not apply here as no domains and other passive information applies within the lab environment. Active reconnaissance will be done and the scanning of the network for live hosts and their open ports. In addition, scanning for the services running on the system, their versions and any potential vulnerabilities with those services. With the information gathered in the reconnaissance phase, an assessment of the vulnerability present on the machine can be done and a plan can develop on how to gain access to the system. After the vulnerability assessment, exploitation of those vulnerabilities can begin to see which ways access to the system can be obtained and once obtained more enumeration of the system can occur to look for ways to escalate privileges with the hope of gaining root access.

### Tools

The following tools will be used to assist with the testing:
- Nmap
- Metasploit
- Searchsploit
- ExploitDB
- CVE Databases
## Vulnerabilities

**Vulnerability 1: ProFTPD Arbitrary read/write of files**  
**ID**: CVE-2015-3306  
**Severity**: Critical  
**Affected systems**: 10.0.69.10, 10.0.69.11  
**Description**: This vulnerability allows for the arbitrary reading or writing of files to the server without authorized access. This can result in unauthorized access using a reverse shell or the loss of confidentiality of the information stored on the system.  
**Proof of Concept:**
![Pasted_image_20241004162604](//assets/Pasted_image_20241004162604.webp)
Utilizing a public exploit in Metasploit framework, it is trivial in gaining access to the webserver as the www-data user. 
**Recommendation**: Update ProFTPD to the latest version to take advantage of the latest security updates.

**Vulnerability 2**: Drupal remote code execution  
**ID**: SA-CONTRIB-2016-039  
**Severity**: Critical  
**Affected Systems**: 10.0.69.10, 10.0.69.11  
**Description**: A flaw in the Drupal service allows for remote code execution without authorization. This can result in unauthorized access to the system, denial of service and other malicious outcomes.  
**Proof of concept**:

![Pasted_image_20241004162659](//assets/Pasted_image_20241004162659.webp)
Utilizing another public exploit in Metasploit framework, it becomes trivial to gain access to the target system as the www-data user.  
**Recommendation**: Update Drupal to the latest version to take advantage of the latest security updates.

**Vulnerability 3**: PwnKit Privilege Escalation  
**ID**: CVE-2021-4034  
**Severity**: High  
**Affected Systems**: 10.0.69.10  
**Description**: Utilizing a flaw in the polkit’s pkexec allowing unprivileged users to run privileged commands, which results in an escalation of privileges to root level.  
**Proof of concept**:  
![Pasted_image_20241004162720](//assets/Pasted_image_20241004162720.webp)
**Recommendations**: Update Linux version to one that is still receiving security updates and takes advantage of any security improvements from modern OS architecture.

**Vulnerability 4**: UnrealIRCD Backdoor  
**ID**: CVE-2010-2075  
**Severity**: High  
**Affected system**: 10.0.69.10  
**Description**: An externally introduced backdoor allows for a remote code execution that can be used to access the machine as the user that is running the service  
**Proof of concept:**  
![Pasted_image_20241004162739](//assets/Pasted_image_20241004162739.webp)
Backdoor allows access to the user that is running UnrealIRC, from here privilege escalation may be possible.  
**Recommendation**: Update UnrealIRC to the latest version to remove the backdoor.

**Vulnerability 5**: VNC blank username, weak password configuration  
**Severity**: Critical, leads to root terminal  
**Affected system**: 10.0.69.11  
**Description**: The credentials for accessing VNC are weak and lead to a root terminal  
**Proof of concept**:  
![Pasted_image_20241004162759](//assets/Pasted_image_20241004162759.webp)
**Recommendation**: Secure VNC access behind stronger credentials. Ensure that VNC is not running at root level.

**Vulnerability 6**: bWAPP Unrestricted file upload  
**Severity**: Critical  
**Affected Systems**: 10.0.69.11, 10.0.69.8  
**Description**: Attacker is allowed to upload any file they want to the affected server  
**Proof of Concept**:  
![Pasted_image_20241004162824](//assets/Pasted_image_20241004162824.webp)
**Vulnerability 7**: File and Directory Traversal  
**Severity**: High  
**Affected Systems**: 10.0.69.11, 10.0.69.8  
**Description**: An attacker is able to format a parameter in the URL to traverse the entire systems file structure and view contents that www-data has access to.  
**Proof of concept**:  
![Pasted_image_20241004162859](//assets/Pasted_image_20241004162859.webp)

**Vulnerability 8**: Anonymous FTP write access  
**Severity**: Critical  
**Affected systems**: 10.0.69.11  
**Description**: Anonymous FTP access allows attacker to upload any file they want to the affected server. Allowing for uploading of reverse shells to be coupled with other services on the system like php.

***For a list of more present vulnerabilities, see the attached appendices for scan outputs.***

## Analysis

Attackers have 3 systems that have ways for an attacker to access the system and the network. These systems are: 10.0.69.8 (Ubuntu Linux), 10.0.69.10 (Linux 3.13), and 10.0.69.11 (Linux 2.6.X). Once inside the network, an attacker will now be aware of any system that is not externally accessible and potentially able to move to systems that were never intended to be accessed by outside people. These systems most likely hold a large amount of confidential data that could be accessed by an attacker. With the types of exploits possible on these machines with them leading to root access, any data on the machine is susceptible to exfiltration, this includes any IP, financial data, non-hashed passwords and even hashed passwords that could be cracked offline. There is an immense risk for a data breach given the nature of the vulnerabilities present in the network. The impact on the business could be substantial, from denial of service attacks to leaking of company data or the sharing of customer data. If left unfixed, the damage to the client could be severe and their reputation may never recover.

## Recommendations

It is recommended that the client keep all systems on its network up to date with the latest versions and security patches. A number of the systems on the network are out of date and have known vulnerabilities associated with the versions. Applications and operating systems are in dire need of updating. Implementing a patch management system will help with staying on top of updates that are vital to securing the network. In addition, the web application hosted on two systems, bWAPP, should not be an externally facing website, it has a large number of vulnerabilities with some leading to direct access to the system. If the website is crucial to business, a security audit and subsequent update should be done to ensure that all vulnerabilities are patched before allowing it to be externally reached. Lastly, some passwords used by the client and its employees are either the default password or easily cracked. It is recommended that a strong security policy be implemented to ensure that trivial access to a system through easy credentials does not occur.

## Conclusion

A complete assessment of the client’s network has been conducted and some critical vulnerabilities were found. 3 of the systems present on the network are susceptible to unauthorized remote access along with possible privilege escalations that result in root access. With the growth the company has been seeing, an increase in attention will be shown resulting an increase in attempted cyber attacks on its infrastructure. It is paramount that the client undergoes all recommendations listed in this report to ensure the safety of its and its customer’s data.

## Appendices

### Appendix 1 – 10.0.69.8 Nmap Scan

┌──(root㉿kali)-[/home/kali]

└─# nmap -sV --script vuln 10.0.69.8

Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-02-15 15:51 EST

Nmap scan report for 10.0.69.8

PORT   STATE SERVICE VERSION

80/tcp open  http    Apache httpd 2.4.52

|_http-server-header: Apache/2.4.52 (Ubuntu)

| http-cross-domain-policy:

|   VULNERABLE:

|   Cross-domain and Client Access policies.

|     State: VULNERABLE

| vulners:

|   cpe:/a:apache:http_server:2.4.52:

|       PACKETSTORM:176334      7.5     https://vulners.com/packetstorm/PACKETSTORM:176334      *EXPLOIT*

|       OSV:BIT-APACHE-2023-25690       7.5     https://vulners.com/osv/OSV:BIT-APACHE-2023-25690

|       OSV:BIT-APACHE-2022-31813       7.5     https://vulners.com/osv/OSV:BIT-APACHE-2022-31813

|       CVE-2023-25690  7.5     https://vulners.com/cve/CVE-2023-25690

|       CVE-2022-31813  7.5     https://vulners.com/cve/CVE-2022-31813

|       CVE-2022-23943  7.5     https://vulners.com/cve/CVE-2022-23943

|       CVE-2022-22720  7.5     https://vulners.com/cve/CVE-2022-22720

|       CNVD-2022-73123 7.5     https://vulners.com/cnvd/CNVD-2022-73123

|       5C1BB960-90C1-5EBF-9BEF-F58BFFDFEED9    7.5     https://vulners.com/githubexploit/5C1BB960-90C1-5EBF-9BEF-F58BFFDFEED9   *EXPLOIT*

|       3F17CA20-788F-5C45-88B3-E12DB2979B7B    7.5     https://vulners.com/githubexploit/3F17CA20-788F-5C45-88B3-E12DB2979B7B   *EXPLOIT*

|       1337DAY-ID-39214        7.5     https://vulners.com/zdt/1337DAY-ID-39214        *EXPLOIT*

| http-enum:

|   /: Root directory w/ listing on 'apache/2.4.52 (ubuntu)'

|_  /crossdomain.xml: Adobe Flash crossdomain policy

|_http-dombased-xss: Couldn't find any DOM based XSS.

| http-sql-injection:

|   Possible sqli for queries:

|     http://10.0.69.8:80/?C=M%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=S%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=N%3BO%3DD%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=D%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=M%3BO%3DD%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=N%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=S%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=D%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=M%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=N%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=S%3BO%3DD%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=D%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=M%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=N%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=S%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=D%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=M%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=N%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=S%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=D%3BO%3DD%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=M%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=N%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=S%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=D%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=M%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=S%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=N%3BO%3DD%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=D%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=M%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=N%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=S%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=D%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=M%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=N%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.8:80/?C=S%3BO%3DA%27%20OR%20sqlspider

|_    http://10.0.69.8:80/?C=D%3BO%3DA%27%20OR%20sqlspider

|_http-stored-xss: Couldn't find any stored XSS vulnerabilities.

| http-csrf:

| Spidering limited to: maxdepth=3; maxpagecount=20; withinhost=10.0.69.8

|   Found the following possible CSRF vulnerabilities:

|     Path: http://10.0.69.8:80/bWAPP/

|     Form id: login

|     Form action: /bWAPP/login.php

|     Path: http://10.0.69.8:80/bWAPP/user_new.php

|     Form id: login

|     Form action: /bWAPP/user_new.php

|     Path: http://10.0.69.8:80/bWAPP/login.php

|     Form id: login

|_    Form action: /bWAPP/login.php

### Appendix 2 – 10.0.69.10 Nmap Scan

┌──(root㉿kali)-[/home/kali]

└─# nmap -sV --script vuln 10.0.69.10             

Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-02-15 15:09 EST

Host is up (0.00022s latency).

Not shown: 991 filtered tcp ports (no-response)

PORT     STATE  SERVICE     VERSION

21/tcp   open   ftp         ProFTPD 1.3.5

| vulners:

|   cpe:/a:proftpd:proftpd:1.3.5:

|       SAINT:FD1752E124A72FD3A26EEB9B315E8382  10.0    https://vulners.com/saint/SAINT:FD1752E124A72FD3A26EEB9B315E8382 *EXPLOIT*

|       PROFTPD_MOD_COPY        10.0    https://vulners.com/canvas/PROFTPD_MOD_COPY     *EXPLOIT*

|       PRION:CVE-2015-3306     10.0    https://vulners.com/prion/PRION:CVE-2015-3306

|       PACKETSTORM:162777      10.0    https://vulners.com/packetstorm/PACKETSTORM:162777      *EXPLOIT*

22/tcp   open   ssh         OpenSSH 6.6.1p1 Ubuntu 2ubuntu2.13 (Ubuntu Linux; protocol 2.0)

| vulners:

|   cpe:/a:openbsd:openssh:6.6.1p1:

|       PRION:CVE-2015-5600     8.5     https://vulners.com/prion/PRION:CVE-2015-5600

|       CVE-2015-5600   8.5     https://vulners.com/cve/CVE-2015-5600

|       PRION:CVE-2020-16088    7.5     https://vulners.com/prion/PRION:CVE-2020-16088

|       PRION:CVE-2015-6564     6.9     https://vulners.com/prion/PRION:CVE-2015-6564

|       CVE-2015-6564   6.9     https://vulners.com/cve/CVE-2015-6564

|       CVE-2018-15919  5.0     https://vulners.com/cve/CVE-2018-15919

|       PRION:CVE-2015-5352     4.3     https://vulners.com/prion/PRION:CVE-2015-5352

|       CVE-2020-14145  4.3     https://vulners.com/cve/CVE-2020-14145

|       CVE-2015-5352   4.3     https://vulners.com/cve/CVE-2015-5352

|       PRION:CVE-2015-6563     1.9     https://vulners.com/prion/PRION:CVE-2015-6563

|_      CVE-2015-6563   1.9     https://vulners.com/cve/CVE-2015-6563

80/tcp   open   http        Apache httpd 2.4.7 ((Ubuntu))

| http-sql-injection:

|   Possible sqli for queries:

|     http://10.0.69.10:80/?C=S%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.10:80/?C=D%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.10:80/?C=N%3BO%3DD%27%20OR%20sqlspider

|_    http://10.0.69.10:80/?C=M%3BO%3DA%27%20OR%20sqlspider

| vulners:

|   cpe:/a:apache:http_server:2.4.7:

|       PACKETSTORM:176334      7.5     https://vulners.com/packetstorm/PACKETSTORM:176334      *EXPLOIT*

|       PACKETSTORM:171631      7.5     https://vulners.com/packetstorm/PACKETSTORM:171631      *EXPLOIT*

|       OSV:BIT-APACHE-2023-25690       7.5     https://vulners.com/osv/OSV:BIT-APACHE-2023-25690

|       OSV:BIT-APACHE-2022-31813       7.5     https://vulners.com/osv/OSV:BIT-APACHE-2022-31813

|       OSV:BIT-APACHE-2022-23943       7.5     https://vulners.com/osv/OSV:BIT-APACHE-2022-23943

|       OSV:BIT-APACHE-2022-22720       7.5     https://vulners.com/osv/OSV:BIT-APACHE-2022-22720

|       OSV:BIT-APACHE-2021-44790       7.5     https://vulners.com/osv/OSV:BIT-APACHE-2021-44790

|       OSV:BIT-APACHE-2021-42013       7.5     https://vulners.com/osv/OSV:BIT-APACHE-2021-42013

|       OSV:BIT-APACHE-2021-41773       7.5     https://vulners.com/osv/OSV:BIT-APACHE-2021-41773

|       OSV:BIT-APACHE-2021-39275       7.5     https://vulners.com/osv/OSV:BIT-APACHE-2021-39275

|       OSV:BIT-APACHE-2021-26691       7.5     https://vulners.com/osv/OSV:BIT-APACHE-2021-26691

|       OSV:BIT-APACHE-2020-11984       7.5     https://vulners.com/osv/OSV:BIT-APACHE-2020-11984

|       MSF:EXPLOIT-MULTI-HTTP-APACHE_NORMALIZE_PATH_RCE-       7.5     https://vulners.com/metasploit/MSF:EXPLOIT-MULTI-HTTP-APACHE_NORMALIZE_PATH_RCE- *EXPLOIT*

|       MSF:AUXILIARY-SCANNER-HTTP-APACHE_NORMALIZE_PATH-       7.5     https://vulners.com/metasploit/MSF:AUXILIARY-SCANNER-HTTP-APACHE_NORMALIZE_PATH- *EXPLOIT*

|       F9C0CD4B-3B60-5720-AE7A-7CC31DB839C5    7.5     https://vulners.com/githubexploit/F9C0CD4B-3B60-5720-AE7A-7CC31DB839C5   *EXPLOIT*

|       EDB-ID:51193    7.5     https://vulners.com/exploitdb/EDB-ID:51193      *EXPLOIT*

|       EDB-ID:50512    7.5     https://vulners.com/exploitdb/EDB-ID:50512      *EXPLOIT*

|       EDB-ID:50446    7.5     https://vulners.com/exploitdb/EDB-ID:50446      *EXPLOIT*

|       EDB-ID:50406    7.5     https://vulners.com/exploitdb/EDB-ID:50406      *EXPLOIT*

|       E796A40A-8A8E-59D1-93FB-78EF4D8B7FA6    7.5     https://vulners.com/githubexploit/E796A40A-8A8E-59D1-93FB-78EF4D8B7FA6   *EXPLOIT*

            |       CVE-2023-25690  7.5     https://vulners.com/cve/CVE-2023-25690

|       CVE-2022-31813  7.5     https://vulners.com/cve/CVE-2022-31813

|       CVE-2022-23943  7.5     https://vulners.com/cve/CVE-2022-23943

|       CVE-2022-22720  7.5     https://vulners.com/cve/CVE-2022-22720

|       CVE-2021-44790  7.5     https://vulners.com/cve/CVE-2021-44790

|       CVE-2021-39275  7.5     https://vulners.com/cve/CVE-2021-39275

|       CVE-2021-26691  7.5     https://vulners.com/cve/CVE-2021-26691

|       CVE-2017-7679   7.5     https://vulners.com/cve/CVE-2017-7679

|       CVE-2017-3167   7.5     https://vulners.com/cve/CVE-2017-3167

|       CNVD-2022-73123 7.5     https://vulners.com/cnvd/CNVD-2022-73123

|       CNVD-2022-03225 7.5     https://vulners.com/cnvd/CNVD-2022-03225

|       CNVD-2021-102386        7.5     https://vulners.com/cnvd/CNVD-2021-102386

|       CC15AE65-B697-525A-AF4B-38B1501CAB49    7.5     https://vulners.com/githubexploit/CC15AE65-B697-525A-AF4B-38B1501CAB49   *EXPLOIT*

|       9B4F4E4A-CFDF-5847-805F-C0BAE809DBD5    7.5     https://vulners.com/githubexploit/9B4F4E4A-CFDF-5847-805F-C0BAE809DBD5   *EXPLOIT*

|       8713FD59-264B-5FD7-8429-3251AB5AB3B8    7.5     https://vulners.com/githubexploit/8713FD59-264B-5FD7-8429-3251AB5AB3B8   *EXPLOIT*

|       6A0A657E-8300-5312-99CE-E11F460B1DBF    7.5     https://vulners.com/githubexploit/6A0A657E-8300-5312-99CE-E11F460B1DBF   *EXPLOIT*

|       61075B23-F713-537A-9B84-7EB9B96CF228    7.5     https://vulners.com/githubexploit/61075B23-F713-537A-9B84-7EB9B96CF228   *EXPLOIT*

|       5C1BB960-90C1-5EBF-9BEF-F58BFFDFEED9    7.5     https://vulners.com/githubexploit/5C1BB960-90C1-5EBF-9BEF-F58BFFDFEED9   *EXPLOIT*

|       5312D04F-9490-5472-84FA-86B3BBDC8928    7.5     https://vulners.com/githubexploit/5312D04F-9490-5472-84FA-86B3BBDC8928   *EXPLOIT*

|       52E13088-9643-5E81-B0A0-B7478BCF1F2C    7.5     https://vulners.com/githubexploit/52E13088-9643-5E81-B0A0-B7478BCF1F2C   *EXPLOIT*

|       3F17CA20-788F-5C45-88B3-E12DB2979B7B    7.5     https://vulners.com/githubexploit/3F17CA20-788F-5C45-88B3-E12DB2979B7B   *EXPLOIT*

|       22DCCD26-B68C-5905-BAC2-71D10DE3F123    7.5     https://vulners.com/githubexploit/22DCCD26-B68C-5905-BAC2-71D10DE3F123   *EXPLOIT*

|       2108729F-1E99-54EF-9A4B-47299FD89FF2    7.5     https://vulners.com/githubexploit/2108729F-1E99-54EF-9A4B-47299FD89FF2   *EXPLOIT*

|       1337DAY-ID-39214        7.5     https://vulners.com/zdt/1337DAY-ID-39214        *EXPLOIT*

|       1337DAY-ID-38427        7.5     https://vulners.com/zdt/1337DAY-ID-38427        *EXPLOIT*

|       1337DAY-ID-37777        7.5     https://vulners.com/zdt/1337DAY-ID-37777        *EXPLOIT*

|       1337DAY-ID-36952        7.5     https://vulners.com/zdt/1337DAY-ID-36952        *EXPLOIT*

|       1337DAY-ID-34882        7.5     https://vulners.com/zdt/1337DAY-ID-34882        *EXPLOIT*

|_http-server-header: Apache/2.4.7 (Ubuntu)

| http-csrf:

| Spidering limited to: maxdepth=3; maxpagecount=20; withinhost=10.0.69.10

|   Found the following possible CSRF vulnerabilities:

|     Path: http://10.0.69.10:80/drupal/

|     Form id: user-login-form

|     Form action: /drupal/?q=node&destination=node

|     Path: http://10.0.69.10:80/payroll_app.php

|     Form id:

|     Form action:    

|     Path: http://10.0.69.10:80/chat/

|     Form id: name

|_    Form action: index.php

|_http-stored-xss: Couldn't find any stored XSS vulnerabilities.

|_http-dombased-xss: Couldn't find any DOM based XSS.

| http-enum:

|   /: Root directory w/ listing on 'apache/2.4.7 (ubuntu)'

|   /phpmyadmin/: phpMyAdmin

|_  /uploads/: Potentially interesting directory w/ listing on 'apache/2.4.7 (ubuntu)'

445/tcp  open   netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)

631/tcp  open   ipp?

|_http-aspnet-debug: ERROR: Script execution failed (use -d to debug)

|_http-vuln-cve2014-3704: ERROR: Script execution failed (use -d to debug)

3000/tcp closed ppp

3306/tcp open   mysql       MySQL (unauthorized)

8080/tcp open   http        Jetty 8.1.7.v20120910

|_http-server-header: Jetty(8.1.7.v20120910)

| http-csrf:

| Spidering limited to: maxdepth=3; maxpagecount=20; withinhost=10.0.69.10

|   Found the following possible CSRF vulnerabilities:

|     Path: http://10.0.69.10:8080/continuum/security/login.action;jsessionid=z1lw8aeghhemya9pt4uxnoth

|     Form id: loginform

|     Form action: /continuum/security/login_submit.action;jsessionid=tmhblfjuu5jh29ixc95jopvy

|     Path: http://10.0.69.10:8080/continuum/security/register.action;jsessionid=tmhblfjuu5jh29ixc95jopvy

|     Form id: registerform

|     Form action: /continuum/security/register_submit.action;jsessionid=tmhblfjuu5jh29ixc95jopvy

|     Path: http://10.0.69.10:8080/continuum/security/login.action;jsessionid=tmhblfjuu5jh29ixc95jopvy

|     Form id: loginform

|     Form action: /continuum/security/login_submit.action;jsessionid=tmhblfjuu5jh29ixc95jopvy

|     Path: http://10.0.69.10:8080/continuum/security/login_submit.action;jsessionid=tmhblfjuu5jh29ixc95jopvy

|     Form id: loginform

|     Form action: /continuum/security/login_submit.action;jsessionid=tmhblfjuu5jh29ixc95jopvy

|     Path: http://10.0.69.10:8080/continuum/security/login.action;jsessionid=z1lw8aeghhemya9pt4uxnoth

|     Form id: loginform

|     Form action: /continuum/security/login_submit.action;jsessionid=tmhblfjuu5jh29ixc95jopvy

|     Path: http://10.0.69.10:8080/continuum/security/passwordReset.action;jsessionid=tmhblfjuu5jh29ixc95jopvy

|     Form id: passwordresetform

|     Form action: /continuum/security/passwordReset_submit.action;jsessionid=tmhblfjuu5jh29ixc95jopvy

|     Path: http://10.0.69.10:8080/continuum/security/login.action;jsessionid=z1lw8aeghhemya9pt4uxnoth

|     Form id: loginform

|     Form action: /continuum/security/login_submit.action;jsessionid=tmhblfjuu5jh29ixc95jopvy

|     Path: http://10.0.69.10:8080/continuum/security/register_submit.action;jsessionid=tmhblfjuu5jh29ixc95jopvy

|     Form id: registerform

|     Form action: /continuum/security/register_submit.action;jsessionid=tmhblfjuu5jh29ixc95jopvy

|     Path: http://10.0.69.10:8080/continuum/security/passwordReset_submit.action;jsessionid=tmhblfjuu5jh29ixc95jopvy

|     Form id: passwordresetform

|_    Form action: /continuum/security/passwordReset_submit.action;jsessionid=tmhblfjuu5jh29ixc95jopvy

|_http-dombased-xss: Couldn't find any DOM based XSS.

|_http-stored-xss: Couldn't find any stored XSS vulnerabilities.

8181/tcp closed intermapper

Host script results:

|_smb-vuln-ms10-054: false

|_smb-vuln-ms10-061: false

| smb-vuln-regsvc-dos:

|   VULNERABLE:

|   Service regsvc in Microsoft Windows systems vulnerable to denial of service

|     State: VULNERABLE

|       The service regsvc in Microsoft Windows 2000 systems is vulnerable to denial of service caused by a null deference

|       pointer. This script will crash the service if it is vulnerable. This vulnerability was discovered by Ron Bowes

|       while working on smb-enum-sessions. 

### Appendix 3 – 10.0.69.11 Nmap Scan

┌──(root㉿kali)-[/home/kali]

└─# nmap -sV --script vuln 10.0.69.11

Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-02-15 16:01 EST

PORT     STATE SERVICE     VERSION

21/tcp   open  ftp         ProFTPD 1.3.1

| vulners:

|   cpe:/a:proftpd:proftpd:1.3.1:

|       SAINT:FD1752E124A72FD3A26EEB9B315E8382  10.0    https://vulners.com/saint/SAINT:FD1752E124A72FD3A26EEB9B315E8382 *EXPLOIT*

|       PROFTPD_MOD_COPY        10.0    https://vulners.com/canvas/PROFTPD_MOD_COPY     *EXPLOIT*

|       PACKETSTORM:162777      10.0    https://vulners.com/packetstorm/PACKETSTORM:162777      *EXPLOIT*

|       EDB-ID:49908    10.0    https://vulners.com/exploitdb/EDB-ID:49908      *EXPLOIT*

|       1337DAY-ID-36298        10.0    https://vulners.com/zdt/1337DAY-ID-36298        *EXPLOIT*

|       1337DAY-ID-23720        10.0    https://vulners.com/zdt/1337DAY-ID-23720        *EXPLOIT*

|       1337DAY-ID-23544        10.0    https://vulners.com/zdt/1337DAY-ID-23544        *EXPLOIT*

|       SSV:26016       9.0     https://vulners.com/seebug/SSV:26016    *EXPLOIT*

|       SSV:24282       9.0     https://vulners.com/seebug/SSV:24282    *EXPLOIT*

|       PRION:CVE-2011-4130     9.0     https://vulners.com/prion/PRION:CVE-2011-4130

|       CVE-2011-4130   9.0     https://vulners.com/cve/CVE-2011-4130

|       SSV:96525       7.5     https://vulners.com/seebug/SSV:96525    *EXPLOIT*

|       PRION:CVE-2009-0542     7.5     https://vulners.com/prion/PRION:CVE-2009-0542

|       CVE-2019-12815  7.5     https://vulners.com/cve/CVE-2019-12815

|       739FE495-4675-5A2A-BB93-EEF94AC07632    7.5     https://vulners.com/githubexploit/739FE495-4675-5A2A-BB93-EEF94AC07632   *EXPLOIT*

22/tcp   open  ssh         OpenSSH 4.7p1 Debian 8ubuntu1 (protocol 2.0)

| vulners:

|   cpe:/a:openbsd:openssh:4.7p1:

|       SSV:78173       7.8     https://vulners.com/seebug/SSV:78173    *EXPLOIT*

|       SSV:69983       7.8     https://vulners.com/seebug/SSV:69983    *EXPLOIT*

|       EDB-ID:24450    7.8     https://vulners.com/exploitdb/EDB-ID:24450      *EXPLOIT*

|       EDB-ID:15215    7.8     https://vulners.com/exploitdb/EDB-ID:15215      *EXPLOIT*

|       SECURITYVULNS:VULN:8166 7.5     https://vulners.com/securityvulns/SECURITYVULNS:VULN:8166

|       PRION:CVE-2010-4478     7.5     https://vulners.com/prion/PRION:CVE-2010-4478

|       CVE-2010-4478   7.5     https://vulners.com/cve/CVE-2010-4478

25/tcp   open  smtp        Postfix smtpd

|_sslv2-drown: ERROR: Script execution failed (use -d to debug)

| smtp-vuln-cve2010-4344:

|_  The SMTP server is not Exim: NOT VULNERABLE

| ssl-dh-params:

|   VULNERABLE:

|   Anonymous Diffie-Hellman Key Exchange MitM Vulnerability

|     State: VULNERABLE

|       Transport Layer Security (TLS) services that use anonymous

|       Diffie-Hellman key exchange only provide protection against passive

|       eavesdropping, and are vulnerable to active man-in-the-middle attacks

|       which could completely compromise the confidentiality and integrity

|       of any data exchanged over the resulting session.

|   Transport Layer Security (TLS) Protocol DHE_EXPORT Ciphers Downgrade MitM (Logjam)

|     State: VULNERABLE

|     IDs:  CVE:CVE-2015-4000  BID:74733

|       The Transport Layer Security (TLS) protocol contains a flaw that is

|       triggered when handling Diffie-Hellman key exchanges defined with

|       the DHE_EXPORT cipher. This may allow a man-in-the-middle attacker

|       to downgrade the security of a TLS session to 512-bit export-grade

|       cryptography, which is significantly weaker, allowing the attacker

|       to more easily break the encryption and monitor or tamper with

|       the encrypted stream.

|   Diffie-Hellman Key Exchange Insufficient Group Strength

|     State: VULNERABLE

|       Transport Layer Security (TLS) services that use Diffie-Hellman groups

|       of insufficient strength, especially those using one of a few commonly

|       shared groups, may be susceptible to passive eavesdropping attacks.

| ssl-poodle:

|   VULNERABLE:

|   SSL POODLE information leak

|     State: VULNERABLE

|     IDs:  CVE:CVE-2014-3566  BID:70574

|           The SSL protocol 3.0, as used in OpenSSL through 1.0.1i and other

|           products, uses nondeterministic CBC padding, which makes it easier

|           for man-in-the-middle attackers to obtain cleartext data via a

|           padding-oracle attack, aka the "POODLE" issue.

|     Disclosure date: 2014-10-14

80/tcp   open  http        Apache httpd 2.2.8 ((Ubuntu) DAV/2 mod_fastcgi/2.4.6 PHP/5.2.4-2ubuntu5 with Suhosin-Patch mod_ssl/2.2.8 OpenSSL/0.9.8g)

| http-cross-domain-policy:

|   VULNERABLE:

|   Cross-domain and Client Access policies.

|     State: VULNERABLE

| vulners:

|   cpe:/a:apache:http_server:2.2.8:

|       SSV:72403       7.8     https://vulners.com/seebug/SSV:72403    *EXPLOIT*

|       SSV:26043       7.8     https://vulners.com/seebug/SSV:26043    *EXPLOIT*

|       SSV:20899       7.8     https://vulners.com/seebug/SSV:20899    *EXPLOIT*

|       PACKETSTORM:126851      7.8     https://vulners.com/packetstorm/PACKETSTORM:126851      *EXPLOIT*

|       PACKETSTORM:123527      7.8     https://vulners.com/packetstorm/PACKETSTORM:123527      *EXPLOIT*

|       PACKETSTORM:122962      7.8     https://vulners.com/packetstorm/PACKETSTORM:122962      *EXPLOIT*

|       EXPLOITPACK:186B5FCF5C57B52642E62C06BABC6F83    7.8     https://vulners.com/exploitpack/EXPLOITPACK:186B5FCF5C57B52642E62C06BABC6F83     *EXPLOIT*

|       EDB-ID:18221    7.8     https://vulners.com/exploitdb/EDB-ID:18221      *EXPLOIT*

|       CVE-2011-3192   7.8     https://vulners.com/cve/CVE-2011-3192

|       1337DAY-ID-21170        7.8     https://vulners.com/zdt/1337DAY-ID-21170        *EXPLOIT*

|       SSV:12673       7.5     https://vulners.com/seebug/SSV:12673    *EXPLOIT*

|       SSV:12626       7.5     https://vulners.com/seebug/SSV:12626    *EXPLOIT*

|       ECC3E825-EE29-59D3-BE28-1B30DB15940E    7.5     https://vulners.com/githubexploit/ECC3E825-EE29-59D3-BE28-1B30DB15940E   *EXPLOIT*

|       CVE-2017-7679   7.5     https://vulners.com/cve/CVE-2017-7679

|       CVE-2017-3167   7.5     https://vulners.com/cve/CVE-2017-3167

| http-sql-injection:

|   Possible sqli for queries:

|     http://10.0.69.11:80/evil/?C=N%3BO%3DD%27%20OR%20sqlspider

|     http://10.0.69.11:80/evil/?C=S%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.11:80/evil/?C=D%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.11:80/evil/?C=M%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.11:80/evil/?C=N%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.11:80/evil/?C=S%3BO%3DA%27%20OR%20sqlspider

|     http://10.0.69.11:80/evil/?C=D%3BO%3DA%27%20OR%20sqlspider

|_    http://10.0.69.11:80/evil/?C=M%3BO%3DA%27%20OR%20sqlspider

|_http-server-header: Apache/2.2.8 (Ubuntu) DAV/2 mod_fastcgi/2.4.6 PHP/5.2.4-2ubuntu5 with Suhosin-Patch mod_ssl/2.2.8 OpenSSL/0.9.8g

| http-csrf:

| Spidering limited to: maxdepth=3; maxpagecount=20; withinhost=10.0.69.11

|   Found the following possible CSRF vulnerabilities:

|     Path: http://10.0.69.11:80/phpmyadmin/

|     Form id:

|     Form action: index.php

|     Path: http://10.0.69.11:80/phpmyadmin/

|     Form id: input_username

|     Form action: index.php

|     Path: http://10.0.69.11:80/drupal/

|     Form id: user-login-form

|     Form action: /drupal/?q=node&destination=node

|     Path: http://10.0.69.11:80/phpmyadmin/index.php

|     Form id:

|     Form action: index.php

|     Path: http://10.0.69.11:80/phpmyadmin/index.php

|     Form id: input_username

|_    Form action: index.php

|_http-dombased-xss: Couldn't find any DOM based XSS.

| http-enum:

|   /crossdomain.xml: Adobe Flash crossdomain policy

|   /phpmyadmin/: phpMyAdmin

|   /README: Interesting, a readme.

|   /README.txt: Interesting, a readme.

|   /icons/: Potentially interesting folder w/ directory listing

|   /server-status/: Potentially interesting folder

|_  /webdav/: Potentially interesting directory w/ listing on 'apache/2.2.8 (ubuntu) dav/2 mod_fastcgi/2.4.6 php/5.2.4-2ubuntu5 with suhosin-patch mod_ssl/2.2.8 openssl/0.9.8g'

|_http-trace: TRACE is enabled

139/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: ITSECGAMES)

443/tcp  open  ssl/http    Apache httpd 2.2.8 ((Ubuntu) DAV/2 mod_fastcgi/2.4.6 PHP/5.2.4-2ubuntu5 with Suhosin-Patch mod_ssl/2.2.8 OpenSSL/0.9.8g)

| ssl-poodle:

|   VULNERABLE:

|   SSL POODLE information leak

|     State: VULNERABLE

|     IDs:  CVE:CVE-2014-3566  BID:70574

|           The SSL protocol 3.0, as used in OpenSSL through 1.0.1i and other

|           products, uses nondeterministic CBC padding, which makes it easier

|           for man-in-the-middle attackers to obtain cleartext data via a

|           padding-oracle attack, aka the "POODLE" issue.

|     Disclosure date: 2014-10-14

|_http-trace: TRACE is enabled

| ssl-ccs-injection:

|   VULNERABLE:

| vulners:

|   cpe:/a:apache:http_server:2.2.8:

|       SSV:72403       7.8     https://vulners.com/seebug/SSV:72403    *EXPLOIT*

|       SSV:26043       7.8     https://vulners.com/seebug/SSV:26043    *EXPLOIT*

|       SSV:20899       7.8     https://vulners.com/seebug/SSV:20899    *EXPLOIT*

|       PACKETSTORM:126851      7.8     https://vulners.com/packetstorm/PACKETSTORM:126851      *EXPLOIT*

|       PACKETSTORM:123527      7.8     https://vulners.com/packetstorm/PACKETSTORM:123527      *EXPLOIT*

|       PACKETSTORM:122962      7.8     https://vulners.com/packetstorm/PACKETSTORM:122962      *EXPLOIT*

|       EXPLOITPACK:186B5FCF5C57B52642E62C06BABC6F83    7.8     https://vulners.com/exploitpack/EXPLOITPACK:186B5FCF5C57B52642E62C06BABC6F83     *EXPLOIT*

|       EDB-ID:18221    7.8     https://vulners.com/exploitdb/EDB-ID:18221      *EXPLOIT*

|       CVE-2011-3192   7.8     https://vulners.com/cve/CVE-2011-3192

|       1337DAY-ID-21170        7.8     https://vulners.com/zdt/1337DAY-ID-21170        *EXPLOIT*

|       SSV:12673       7.5     https://vulners.com/seebug/SSV:12673    *EXPLOIT*

|       SSV:12626       7.5     https://vulners.com/seebug/SSV:12626    *EXPLOIT*

|       ECC3E825-EE29-59D3-BE28-1B30DB15940E    7.5     https://vulners.com/githubexploit/ECC3E825-EE29-59D3-BE28-1B30DB15940E   *EXPLOIT*

|       CVE-2017-7679   7.5     https://vulners.com/cve/CVE-2017-7679

|       CVE-2017-3167   7.5     https://vulners.com/cve/CVE-2017-3167

| ssl-dh-params:

|   VULNERABLE:

|   Transport Layer Security (TLS) Protocol DHE_EXPORT Ciphers Downgrade MitM (Logjam)

|     State: VULNERABLE

|     IDs:  CVE:CVE-2015-4000  BID:74733

|       The Transport Layer Security (TLS) protocol contains a flaw that is

|       triggered when handling Diffie-Hellman key exchanges defined with

|       the DHE_EXPORT cipher. This may allow a man-in-the-middle attacker

|       to downgrade the security of a TLS session to 512-bit export-grade

|       cryptography, which is significantly weaker, allowing the attacker

|       to more easily break the encryption and monitor or tamper with

|       the encrypted stream.

|     Disclosure date: 2015-5-19

|   Diffie-Hellman Key Exchange Insufficient Group Strength

|     State: VULNERABLE

|       Transport Layer Security (TLS) services that use Diffie-Hellman groups

|       of insufficient strength, especially those using one of a few commonly

|       shared groups, may be susceptible to passive eavesdropping attacks.

| http-cross-domain-policy:

|   VULNERABLE:

| http-enum:

|   /crossdomain.xml: Adobe Flash crossdomain policy

|   /phpmyadmin/: phpMyAdmin

|   /README: Interesting, a readme.

|   /README.txt: Interesting, a readme.

|   /icons/: Potentially interesting folder w/ directory listing

|   /server-status/: Potentially interesting folder

|_  /webdav/: Potentially interesting directory w/ listing on 'apache/2.2.8 (ubuntu) dav/2 mod_fastcgi/2.4.6 php/5.2.4-2ubuntu5 with suhosin-patch mod_ssl/2.2.8 openssl/0.9.8g'

|_sslv2-drown: ERROR: Script execution failed (use -d to debug)

445/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: ITSECGAMES)

512/tcp  open  exec        netkit-rsh rexecd

513/tcp  open  login?

514/tcp  open  shell?

666/tcp  open  doom?

| fingerprint-strings:

|   GenericLines, beast2:

|     *** bWAPP Movie Service ***

|_    Matching movies: 0

3306/tcp open  mysql       MySQL 5.0.96-0ubuntu3

|_mysql-vuln-cve2012-2122: ERROR: Script execution failed (use -d to debug)

| vulners:

|   MySQL 5.0.96-0ubuntu3:

|       CVE-2009-0819   4.0     https://vulners.com/cve/CVE-2009-0819

|_      CVE-2007-5925   4.0     https://vulners.com/cve/CVE-2007-5925

5901/tcp open  vnc         VNC (protocol 3.8)

6001/tcp open  X11         (access denied)

8080/tcp open  http        nginx 1.4.0

| http-vuln-cve2011-3192:

|   VULNERABLE:

|   Apache byterange filter DoS

|     State: VULNERABLE

|     IDs:  CVE:CVE-2011-3192  BID:49303

|       The Apache web server is vulnerable to a denial of service attack when numerous

|       overlapping byte ranges are requested.

|     Disclosure date: 2011-08-19

| http-enum:

|_  /crossdomain.xml: Adobe Flash crossdomain policy

|_http-server-header: nginx/1.4.0

| http-cross-domain-policy:

|   VULNERABLE:

| http-csrf:

| Spidering limited to: maxdepth=3; maxpagecount=20; withinhost=10.0.69.11

|   Found the following possible CSRF vulnerabilities:

|     Path: http://10.0.69.11:8080/drupal/

|     Form id: user-login-form

|     Form action: /drupal/?q=node&destination=node

|     Path: http://10.0.69.11:8080/drupal/

|     Form id: user-login-form

|     Form action: /drupal/?q=node&destination=node

|     Path: http://10.0.69.11:8080/drupal/?q=node&amp;destination=node

|     Form id: user-login-form

|     Form action: /drupal/?q=node&destination=node%3Famp%253Bdestination%3Dnode

|     Path: http://10.0.69.11:8080/drupal/?q=user/register

|     Form id: user-register-form

|     Form action: /drupal/index.php?q=user/register

|     Path: http://10.0.69.11:8080/drupal/?q=user/password

|     Form id: user-pass

|     Form action: /drupal/index.php?q=user/password

|     Path: http://10.0.69.11:8080/sqlite/main.php?

|     Form id:

|     Form action: main.php

|     Path: http://10.0.69.11:8080/sqlite/main.php?

|     Form id:

|     Form action: main.php 

|     Path: http://10.0.69.11:8080/drupal/?q=node&amp;destination=node%3Famp%253Bdestination%3Dnode

|     Form id: user-login-form

|     Form action: /drupal/?q=node&destination=node%3Famp%253Bdestination%3Dnode%253Famp%25253Bdestination%253Dnode

|     Path: http://10.0.69.11:8080/drupal/index.php?q=user/register

|     Form id: user-register-form

|     Form action: /drupal/index.php?q=user/register

|     Path: http://10.0.69.11:8080/drupal/?q=user

|     Form id: user-login

|     Form action: /drupal/index.php?q=user

|     Path: http://10.0.69.11:8080/drupal/index.php?q=user/password

|     Form id: user-pass

|     Form action: /drupal/index.php?q=user/password

|     Path: http://10.0.69.11:8080/sqlite/main.php

|     Form id:

|     Form action: main.php

|     Path: http://10.0.69.11:8080/sqlite/main.php

|     Form id:

|_    Form action: main.php

| vulners:

|   cpe:/a:igor_sysoev:nginx:1.4.0:

|       SSV:85572       7.5     https://vulners.com/seebug/SSV:85572    *EXPLOIT*

|       SSV:79160       7.5     https://vulners.com/seebug/SSV:79160    *EXPLOIT*

|       SSV:60785       7.5     https://vulners.com/seebug/SSV:60785    *EXPLOIT*

|       SECURITYVULNS:VULN:13417        7.5     https://vulners.com/securityvulns/SECURITYVULNS:VULN:13417

|       SECURITYVULNS:VULN:13164        7.5     https://vulners.com/securityvulns/SECURITYVULNS:VULN:13164

|       PRION:CVE-2014-0133     7.5     https://vulners.com/prion/PRION:CVE-2014-0133

|       PRION:CVE-2013-4547     7.5     https://vulners.com/prion/PRION:CVE-2013-4547

|       PRION:CVE-2013-2028     7.5     https://vulners.com/prion/PRION:CVE-2013-2028

|       PACKETSTORM:122477      7.5     https://vulners.com/packetstorm/PACKETSTORM:122477      *EXPLOIT*

|       PACKETSTORM:121712      7.5     https://vulners.com/packetstorm/PACKETSTORM:121712      *EXPLOIT*

|       PACKETSTORM:121675      7.5     https://vulners.com/packetstorm/PACKETSTORM:121675      *EXPLOIT*

|       NGINX_CHUNK     7.5     https://vulners.com/canvas/NGINX_CHUNK  *EXPLOIT*

|       NGINX:CVE-2013-2028     7.5     https://vulners.com/nginx/NGINX:CVE-2013-2028

|       EXPLOITPACK:BB1C2509A747FBDC196EEFC68B5C31A8    7.5     https://vulners.com/exploitpack/EXPLOITPACK:BB1C2509A747FBDC196EEFC68B5C31A8     *EXPLOIT*

|       EXPLOITPACK:5BF13177C7F5319A339BD02C026AC260    7.5     https://vulners.com/exploitpack/EXPLOITPACK:5BF13177C7F5319A339BD02C026AC260     *EXPLOIT*

|       EDB-ID:32277    7.5     https://vulners.com/exploitdb/EDB-ID:32277      *EXPLOIT*

|       EDB-ID:25499    7.5     https://vulners.com/exploitdb/EDB-ID:25499      *EXPLOIT*

|       1337DAY-ID-20798        7.5     https://vulners.com/zdt/1337DAY-ID-20798       

| http-sql-injection:

|   Possible sqli for queries:

|_    http://10.0.69.11:8080/sqlite/index.php?dbsel=1%27%20OR%20sqlspider

8443/tcp open  ssl/http    nginx 1.4.0

| vulners:

|   cpe:/a:igor_sysoev:nginx:1.4.0:

|       SSV:85572       7.5     https://vulners.com/seebug/SSV:85572    *EXPLOIT*

|       SSV:79160       7.5     https://vulners.com/seebug/SSV:79160    *EXPLOIT*

|       SSV:60785       7.5     https://vulners.com/seebug/SSV:60785    *EXPLOIT*

|       SECURITYVULNS:VULN:13417        7.5     https://vulners.com/securityvulns/SECURITYVULNS:VULN:13417

|       SECURITYVULNS:VULN:13164        7.5     https://vulners.com/securityvulns/SECURITYVULNS:VULN:13164

|       PRION:CVE-2014-0133     7.5     https://vulners.com/prion/PRION:CVE-2014-0133

|       PRION:CVE-2013-4547     7.5     https://vulners.com/prion/PRION:CVE-2013-4547

|       PRION:CVE-2013-2028     7.5     https://vulners.com/prion/PRION:CVE-2013-2028

|       PACKETSTORM:122477      7.5     https://vulners.com/packetstorm/PACKETSTORM:122477      *EXPLOIT*

|       PACKETSTORM:121712      7.5     https://vulners.com/packetstorm/PACKETSTORM:121712      *EXPLOIT*

|       PACKETSTORM:121675      7.5     https://vulners.com/packetstorm/PACKETSTORM:121675      *EXPLOIT*

|       NGINX_CHUNK     7.5     https://vulners.com/canvas/NGINX_CHUNK  *EXPLOIT*

|       NGINX:CVE-2013-2028     7.5     https://vulners.com/nginx/NGINX:CVE-2013-2028

|       EXPLOITPACK:BB1C2509A747FBDC196EEFC68B5C31A8    7.5     https://vulners.com/exploitpack/EXPLOITPACK:BB1C2509A747FBDC196EEFC68B5C31A8     *EXPLOIT*

|       EXPLOITPACK:5BF13177C7F5319A339BD02C026AC260    7.5     https://vulners.com/exploitpack/EXPLOITPACK:5BF13177C7F5319A339BD02C026AC260     *EXPLOIT*

|       EDB-ID:32277    7.5     https://vulners.com/exploitdb/EDB-ID:32277      *EXPLOIT*

|       EDB-ID:25499    7.5     https://vulners.com/exploitdb/EDB-ID:25499      *EXPLOIT*

|       1337DAY-ID-20798        7.5     https://vulners.com/zdt/1337DAY-ID-20798        *EXPLOIT*

| http-cross-domain-policy:

|   VULNERABLE:

|   Cross-domain and Client Access policies.

|     State: VULNERABLE

| http-enum:

|_  /crossdomain.xml: Adobe Flash crossdomain policy

|_http-dombased-xss: Couldn't find any DOM based XSS.

|_http-server-header: nginx/1.4.0

| http-vuln-cve2011-3192:

|   VULNERABLE:

|   Apache byterange filter DoS

|     State: VULNERABLE

|     IDs:  CVE:CVE-2011-3192  BID:49303

|       The Apache web server is vulnerable to a denial of service attack when numerous

|       overlapping byte ranges are requested.

| ssl-poodle:

|   VULNERABLE:

|   SSL POODLE information leak

|     State: VULNERABLE

|     IDs:  CVE:CVE-2014-3566  BID:70574

|           The SSL protocol 3.0, as used in OpenSSL through 1.0.1i and other

|           products, uses nondeterministic CBC padding, which makes it easier

|           for man-in-the-middle attackers to obtain cleartext data via a

|           padding-oracle attack, aka the "POODLE" issue.

|     Disclosure date: 2014-10-14

|     Check results:

|       TLS_RSA_WITH_AES_128_CBC_SHA

| ssl-dh-params:

|   VULNERABLE:

|   Diffie-Hellman Key Exchange Insufficient Group Strength

|     State: VULNERABLE

|       Transport Layer Security (TLS) services that use Diffie-Hellman groups

|       of insufficient strength, especially those using one of a few commonly

|       shared groups, may be susceptible to passive eavesdropping attacks.

| ssl-heartbleed:

|   VULNERABLE:

|   The Heartbleed Bug is a serious vulnerability in the popular OpenSSL cryptographic software library. It allows for stealing information intended to be protected by SSL/TLS encryption.

|     State: VULNERABLE

|     Risk factor: High

|       OpenSSL versions 1.0.1 and 1.0.2-beta releases (including 1.0.1f and 1.0.2-beta1) of OpenSSL are affected by the Heartbleed bug. The bug allows for reading memory of systems protected by the vulnerable OpenSSL versions and could allow for disclosure of otherwise encrypted confidential information as well as the encryption keys themselves.

| ssl-ccs-injection:

|   VULNERABLE:

|   SSL/TLS MITM vulnerability (CCS Injection)

|     State: VULNERABLE

|     Risk factor: High

|       OpenSSL before 0.9.8za, 1.0.0 before 1.0.0m, and 1.0.1 before 1.0.1h

|       does not properly restrict processing of ChangeCipherSpec messages,

|       which allows man-in-the-middle attackers to trigger use of a zero

|       length master key in certain OpenSSL-to-OpenSSL communications, and

|       consequently hijack sessions or obtain sensitive information, via

|       a crafted TLS handshake, aka the "CCS Injection" vulnerability.

9080/tcp open  http        lighttpd 1.4.19

| http-sql-injection:

|   Possible sqli for queries:

|_    http://10.0.69.11:9080/sqlite/index.php?dbsel=1%27%20OR%20sqlspider

| http-csrf:

| Spidering limited to: maxdepth=3; maxpagecount=20; withinhost=10.0.69.11

|   Found the following possible CSRF vulnerabilities:

|     Path: http://10.0.69.11:9080/drupal/

|     Form id: user-login-form

|     Form action: /drupal/?q=node&destination=node

|     Path: http://10.0.69.11:9080/drupal/

|     Form id: user-login-form

|     Form action: /drupal/?q=node&destination=node

|     Path: http://10.0.69.11:9080/drupal/?q=user/register

|     Form id: user-register-form

|     Form action: /drupal/?q=user/register

|     Path: http://10.0.69.11:9080/drupal/?q=node&amp;destination=node

|     Form id: user-login-form

|     Form action: /drupal/?q=node&destination=node%3Famp%253Bdestination%3Dnode

|     Path: http://10.0.69.11:9080/drupal/?q=user/password

|     Form id: user-pass

|     Form action: /drupal/?q=user/password

|     Path: http://10.0.69.11:9080/sqlite/main.php?

|     Form id:

|     Form action: main.php

|     Path: http://10.0.69.11:9080/sqlite/main.php?

|     Form id:

|     Form action: main.php

|     Path: http://10.0.69.11:9080/evil/sandbox.htm

|     Form id: login

|_    Form action: http://attacker.com/catch.php?

| http-enum:

|   /crossdomain.xml: Adobe Flash crossdomain policy

|_  /README.txt: Interesting, a readme.

| http-cross-domain-policy:

|   VULNERABLE:

| vulners:

|   cpe:/a:lighttpd:lighttpd:1.4.19:

|       SSV:4168        7.8     https://vulners.com/seebug/SSV:4168     *EXPLOIT*

|       PRION:CVE-2013-4559     7.6     https://vulners.com/prion/PRION:CVE-2013-4559

|       CVE-2013-4559   7.6     https://vulners.com/cve/CVE-2013-4559

|       SSV:61980       7.5     https://vulners.com/seebug/SSV:61980    *EXPLOIT*

|       SSV:4167        7.5     https://vulners.com/seebug/SSV:4167     *EXPLOIT*

|       PRION:CVE-2019-11072    7.5     https://vulners.com/prion/PRION:CVE-2019-11072

|       PRION:CVE-2014-2323     7.5     https://vulners.com/prion/PRION:CVE-2014-2323

|       PRION:CVE-2008-4360     7.5     https://vulners.com/prion/PRION:CVE-2008-4360

|       PRION:CVE-2008-4359     7.5     https://vulners.com/prion/PRION:CVE-2008-4359

|       CVE-2019-11072  7.5     https://vulners.com/cve/CVE-2019-11072

|       CVE-2014-2323   7.5     https://vulners.com/cve/CVE-2014-2323

|       CVE-2008-4360   7.5     https://vulners.com/cve/CVE-2008-4360

|       CVE-2008-4359   7.5     https://vulners.com/cve/CVE-2008-4359

|_http-server-header: lighttpd/1.4.19
