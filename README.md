# Enumeration Lab

## Objective

The Enumeration lab is aimed to showcase the key details that can be extracted through successful enumeration. This includes information like operating systems, network infrastructure details, user accounts, shared resources, and more. This information is vital for understanding the system's attack surface. The lab is also meant to emphasize how enumeration allows us to gather valuable information about a system's configuration, user accounts, and potential vulnerabilities. This knowledge is crucial for ethical hackers and penetration testers to identify weaknesses before malicious actors do.


### Skills Learned

- Enumeration concept
- Kali Linux
- Nmap
- Firewalls Intrusion Detection System (IDS) and Intrusion Prevention System (IPS)
- Vulnerability Assesment

### Tools Used

- Operative System Linux
- Nmap, network mapper tool used for network discovery and security auditing.

## Enumeration

Enumeration is the process of systematically probing a target for information. It's a crucial tool for
hackers. This information can help them target attacks more effectively and minimize collateral damage.
Enumeration is one of the most important steps in ethical hacking because it gives hackers the
information they need to launch an attack. For example, hackers who want to crack passwords
need to know the usernames of valid users on that system (CrashTestSecurity.com, 2022).

When it comes to network security, enumeration is a key process. By enumerating a system, you
can gain a better understanding of that system and how it works. This knowledge can then be used
to exploit vulnerabilities and gain access to confidential data.

### Enumeration Techniques
Several techniques can be used for enumeration, and the specific method depends on the type of
system you are targeting. The most common methods include:
Email IDs and Usernames: This involves collecting information about a system by identifying email
addresses and usernames. This information can be used to brute-force passwords or gain access to
sensitive data.
Default Passwords: Another common method is identifying default passwords that may not have
been changed. Exploiting these default credentials allows access to systems that are not properly
secured.

Successful enumeration can provide details like:
- Operating System Details
- Network Infrastructure Details
- Valid Usernames
- Machine Names
- Shared Resource Names
- Directory Names
- Printer Names
- Web Server Details

This practical case will demonstrate how to scan for active hosts in a network using the Nmap tool
on a Kali Linux system.

## Steps
1.	Launch Kali Linux with root privileges.
2.	Execute the following command to initiate the scan: nmap -sP 192.168.01/24
   
   ![image](https://github.com/Fabian-R/Enumeration-Lab/assets/169630952/e3a17856-255d-46ff-9f0b-58b70b87a496)

*Ref 1: Nmap command execution*

-	-sP instructs Nmap to perform a ping scan, which identifies active hosts by sending ICMP (Internet Control Message Protocol) echo requests and analyzing the responses.The -sP option is recommended by the EC-Council as an initial step in network scanning, as it provides a quick and non-intrusive way to identify active hosts.
- 192.168.01/24 specifies the target network range, in this case, the class C network 192.168.0.1 to 192.168.0.254
- The scan will output a list of active hosts within the specified network range, along with their IP addresses. This information can be used for further network security analysis and potential penetration testing activities. 

To delve deeper into the network reconnaissance, we can expand our scan by incorporating the following command:  nmap -O 192.168.0.1/24
-	-O introduces the operating system detection capability, instructing nmap to attempt to identify the operating systems running on the active hosts within the specified network range.

![image](https://github.com/Fabian-R/Enumeration-Lab/assets/169630952/e1d19601-170c-41ea-b7b8-ecc0650357ff)

*Ref 2: Nmap command execution with -o variable*


  
By combining the ping scan (nmap -sP) and operating system detection scan (nmap -O), we obtain a comprehensive overview of the active hosts in the network, along with their respective operating systems. This information serves as a solid foundation for further network security analysis and potential penetration testing endeavors. Based on this, the attacker could have initiated a privilege escalation through the Windows Server by identifying open ports. Combined with tools like Wireshark, they could capture packets that the hosts send to the server or a website through DNS capture. They could have also established a MiTM attack where all network traffic passes through their device by modifying ARP tables.

### Results

In this scenario, to prevent a scan attack like this, firewalls such as Intrusion Detection System (IDS) or Intrusion Prevention System (IPS) can be established. They monitor all network traffic to identify any known malicious behavior. One of the ways an attacker will try to compromise a network is by exploiting a vulnerability within a device or within the software. IDS/IPS identifies these exploitation attempts and blocks them before they successfully compromise any endpoint within the network. They also detect suspicious or unauthorized activities, such as phishing attacks, virus infection and distribution, malware and ransomware installation and download, denial of service (DoS), man-in-the-middle attacks, zero-day attacks, SQL injection, among others.

Factors Influencing Enumeration
-	As seen in the previous example, there is no specific way or single path when carrying out these types of processes. Part of what determines how and what tools will be used depends on these factors:
-	Scan Objective: The purpose of the scan, whether it's to identify active hosts, vulnerabilities, or specific services.
-	Available Time: The amount of time available to conduct the scan, which may influence the choice of tools and techniques.
-	Risk Level: The perceived risk level associated with the scan, which may dictate the level of aggressiveness and depth of the enumeration.

To enhance the effectiveness of enumeration, the following recommendations can be considered:
-	Utilize a Combination of Scanning Techniques: Employ a variety of scanning techniques to gain a comprehensive understanding of the network.
-	Document Scan Results: Thoroughly document the findings of the scan to facilitate subsequent analysis and review.
-	Possess Basic Networking Knowledge: It is fundamental to understand networking concepts to accurately interpret scan results.

### Bibliography

- NMAP.org. (s.f.). Chapter 1. Getting Started with Nmap. Obtain from https://nmap.org/book/intro.html NMAP.org. (s.f.).
- Chapter 11. Defenses Against Nmap. Obtain from https://nmap.org/book/defenses.html
- NMAP.org. (s.f.). Firewall/IDS Evasion and Spoofing. Obtain from https://nmap.org/book/manbypass-firewalls-ids.html
- NMAP.org. (s.f.). Port Scanning Techniques. Obtain from https://nmap.org/book/man-portscanning-techniques.html
- NMAP.org. (s.f.). TCP SYN (Stealth) Scan (-sS). Obtain from https://nmap.org/book/synscan.html
- CrashTestSecurity. (2022, May 9). What is enumeration in hacking? – cyber security blog. Obtain from https://crashtest-security.com/enumeration-cyber-security/
