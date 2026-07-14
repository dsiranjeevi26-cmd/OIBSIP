# Common Network Security Threats

## Research Report

**Name:** Siranjeevi D

**Internship:** Oasis Infobyte Cyber Security Internship

**Task:** Task 4 – Research Report: Common Network Security Threats

**Date:** July 2026

--------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------

## Introduction

As organizations increasingly rely on digital technologies, computer networks have become critical for communication, business operations, and data storage. This growing dependence has also increased the risk of cyberattacks targeting network infrastructure. Network security threats such as Denial-of-Service (DoS), Distributed Denial-of-Service (DDoS), Man-in-the-Middle (MITM), IP Spoofing, and DNS Poisoning can disrupt services, compromise sensitive information, and cause significant financial and reputational damage. Understanding how these attacks work and implementing effective security measures are essential for protecting modern networks and ensuring the confidentiality, integrity, and availability of information.

## 1. DoS Attacks

### Definition

A denial-of-service (DoS) attack is a type of cyber attack in which a malicious actor aims to render a computer or other device unavailable to its intended users by interrupting the device's normal functioning. DoS attacks typically function by overwhelming or flooding a targeted machine with requests until normal traffic is unable to be processed, resulting in denial-of-service to addition users. A DoS attack is characterized by using a single computer to launch the attack.

### How the Attack Works

The primary focus of a DoS attack is to oversaturate the capacity of a targeted machine, resulting in denial-of-service to additional requests. The multiple attack vectors of DoS attacks can be grouped by their similarities.

DoS attacks typically fall in 2 categories:

### Buffer overflow attacks

An attack type in which a memory buffer overflow can cause a machine to consume all available hard disk space, memory, or CPU time. This form of exploit often results in sluggish behavior, system crashes, or other deleterious server behaviors, resulting in denial-of-service.

### Flood attacks

By saturating a targeted server with an overwhelming amount of packets, a malicious actor is able to oversaturate server capacity, resulting in denial-of-service. In order for most DoS flood attacks to be successful, the malicious actor must have more available bandwidth than the target.


 ### Real-World Example: Panix TCP SYN Flood Attack (1996)

In September 1996, Panix, one of the oldest Internet Service Providers (ISPs) in New York, became the target of one of the first publicly documented Denial-of-Service (DoS) attacks. The attacker launched a **TCP SYN flood attack**, which exploited the TCP three-way handshake process.

The attacker sent a large number of TCP SYN (synchronization) packets to Panix's servers but never completed the connection by sending the final ACK packet. As a result, the server kept thousands of half-open connections in memory while waiting for responses that never arrived. Eventually, the server's connection queue became full, preventing legitimate users from establishing new connections.

The attack caused significant service disruption, making Panix's online services unavailable for an extended period. This incident highlighted the weaknesses of the TCP protocol against SYN flood attacks and encouraged the development of security mechanisms such as SYN cookies, improved firewall filtering, and intrusion detection systems to protect against similar attacks.

 
 ### Impact

 A Denial-of-Service (DoS) attack can significantly affect the availability and performance of a targeted system. The major impacts include:

1.Service Unavailability: The targeted server or website becomes slow or completely inaccessible to legitimate users.

2.Business Disruption: Organizations may experience interruptions in their daily operations, affecting customer services and business activities.

3.Financial Loss: Downtime can result in lost sales, reduced productivity, and additional costs for system recovery.

4.Customer Dissatisfaction: Users may lose trust in the organization if its online services remain unavailable for an extended period.

5.Resource Exhaustion: The attack consumes the server's CPU, memory, and network bandwidth, reducing its ability to process legitimate requests.

### Mitigation

Implement Firewalls and Intrusion Prevention Systems (IPS): Firewalls and IPS solutions can monitor incoming traffic, detect suspicious activity, and block malicious requests before they reach the target server.

Apply Rate Limiting: Rate limiting restricts the number of requests a single IP address can send within a specific time period. This helps prevent attackers from overwhelming the server with excessive traffic.

Continuously Monitor Network Traffic: Regular monitoring of network traffic enables administrators to identify unusual spikes in activity and respond quickly to potential DoS attacks before they cause significant disruption.

-------------------------------------------------------------------------
-------------------------------------------------------------------------
 
### DDos Attack

### Definition

A distributed denial-of-service (DDoS) attack is a malicious attempt to disrupt the normal traffic of a targeted server, service, or network by overwhelming the target or its surrounding infrastructure with a flood of Internet traffic.
DDoS attacks achieve effectiveness by utilizing multiple compromised computer systems as sources of attack traffic. Exploited machines can include computers and other networked resources such as IoT devices.
From a high level, a DDoS attack is like an unexpected traffic jam clogging up the highway, preventing regular traffic from arriving at its destination.

### How the Attack Works

DDoS attacks are carried out with networks of Internet-connected machines. These networks consist of computers and other devices (such as IoT devices) which have been infected with malware, allowing them to be controlled remotely by an attacker. These individual devices are referred to as bots (or zombies), and a group of bots is known as a botnet.

Once a botnet has been established, the attacker is able to direct an attack by sending remote instructions to each bot. When a victim's server or network is targeted by the botnet, each bot sends requests to the target's IP address, potentially causing the server or network to become overwhelmed, resulting in a denial-of-service to normal traffic.

### Real-World Example: GitHub DDoS Attack (2018)

On **February 28, 2018**, GitHub experienced one of the largest Distributed Denial-of-Service (DDoS) attacks recorded at that time. The attack reached a peak traffic volume of approximately **1.35 terabits per second (Tbps)**. Attackers exploited vulnerable **Memcached** servers to amplify network traffic and flood GitHub's servers with a massive number of requests.

The overwhelming traffic temporarily affected GitHub's availability and prevented legitimate users from accessing its services. GitHub quickly responded by redirecting traffic through a DDoS mitigation service, which filtered the malicious traffic and restored normal operations within about **10 minutes**.

This incident demonstrated how attackers can use amplification techniques to generate extremely large amounts of traffic and highlighted the importance of DDoS protection services, traffic filtering, and continuous network monitoring.


 ### Impact

A Distributed Denial-of-Service (DDoS) attack can have severe consequences for organizations and online services. The major impacts include:

**Service Downtime:** A DDoS attack can make websites, applications, or online services unavailable to legitimate users by overwhelming the target with excessive traffic.

**Financial Loss:** Organizations may suffer significant financial losses due to interrupted business operations, lost sales, and the costs associated with mitigating and recovering from the attack.

 **Reputational Damage:** Frequent or prolonged service outages can reduce customer trust and negatively affect an organization's reputation.

**Resource Exhaustion:** The attack consumes network bandwidth, CPU, memory, and server resources, preventing the system from processing legitimate user requests.

**Reduced Productivity:** Employees and customers may be unable to access critical online services, leading to delays and decreased operational efficiency.

### Mitigation

The key concern in mitigating a DDoS attack is differentiating between attack traffic and normal traffic. Several strategies exist:

Rate limiting: Limiting the number of requests a server will accept over a certain time window

Web Application Firewall (WAF): A tool that filters traffic based on a series of rules

Anycast network diffusion: Using an Anycast network to scatter the attack traffic across a distributed network

Blackhole routing: Creating a blackhole route and funneling traffic into it.

--------------------------------------------------------------------------------
--------------------------------------------------------------------------------

###  Man-in-the-Middle (MITM) Attacks

### Definition

A **Man-in-the-Middle (MITM) attack** is a type of cyberattack in which an attacker secretly intercepts, monitors, or alters the communication between two parties without their knowledge. The attacker positions themselves between the sender and the receiver, allowing them to steal sensitive information such as usernames, passwords, credit card details, and confidential data. MITM attacks commonly occur on unsecured public Wi-Fi networks, through ARP spoofing, DNS spoofing, or by using malicious access points.

### How the Attack Works

A Man-in-the-Middle (MITM) attack occurs when an attacker secretly positions themselves between a user and a legitimate server or website. The attacker intercepts the communication without the knowledge of either party.

The attack typically works as follows:

 The victim attempts to connect to a legitimate website, application, or network.
 The attacker intercepts the connection by exploiting an unsecured public Wi-Fi network, using ARP spoofing, DNS spoofing, or setting up a rogue Wi-Fi access point.
 Instead of communicating directly with the intended server, the victim's data passes through the attacker's system.
 The attacker can monitor, capture, or modify the transmitted data, including usernames, passwords, banking information, and other confidential information.
 After intercepting the data, the attacker forwards it to the legitimate server, making both the victim and the server believe they are communicating directly with each other.

### Real-World Example: Lenovo Superfish Incident (2015)

In 2015, Lenovo discovered that some of its consumer laptops were shipped with pre-installed software called **Superfish Visual Discovery**. The software installed its own self-signed root certificate on users' computers, allowing it to intercept encrypted HTTPS communications between users and websites. This effectively created a **Man-in-the-Middle (MITM)** vulnerability.

Because the same private encryption key was used on all affected devices, attackers could exploit this weakness to intercept secure communications, steal sensitive information such as usernames, passwords, and banking details, or inject malicious content into web pages. After the vulnerability was publicly disclosed, Lenovo stopped shipping the software, released a removal tool, and published security updates to protect affected users.

This incident demonstrated how improperly implemented software could compromise encrypted communications and expose users to serious security risks.

### Impact

A Man-in-the-Middle (MITM) attack can have serious consequences for both individuals and organizations. The major impacts include:

**Data Theft:** Attackers can intercept and steal sensitive information such as usernames, passwords, credit card details, banking information, and personal data.

**Identity Theft:** Stolen personal information can be used to impersonate victims, commit fraud, or gain unauthorized access to online accounts.

**Financial Loss:** Individuals and organizations may suffer financial losses due to unauthorized transactions, fraud, or recovery costs after a successful attack.

**Loss of Privacy:** Private communications, emails, and confidential business information can be monitored or modified without the knowledge of the sender or receiver.

**Reputational Damage:** Organizations that experience MITM attacks may lose customer trust and damage their reputation if sensitive customer information is compromised.

### Mitigation Strategies

The following measures can help prevent Man-in-the-Middle (MITM) attacks:

 **Use HTTPS and SSL/TLS Encryption**

Always access websites that use HTTPS instead of HTTP. SSL/TLS encryption protects data transmitted between users and web servers, making it difficult for attackers to intercept or modify communications.

 **Avoid Unsecured Public Wi-Fi or Use a VPN**

 Public Wi-Fi networks are common targets for MITM attacks. When using public networks, connect through a trusted Virtual Private Network (VPN) to encrypt internet traffic and protect sensitive information.

**Enable Multi-Factor Authentication (MFA)**

Multi-Factor Authentication adds an additional layer of security by requiring a second verification method, such as a one-time password (OTP) or authentication app. Even if an attacker steals a user's password, they cannot easily access the account without the second authentication factor.

--------------------------------------------------------------------------------
--------------------------------------------------------------------------------

### IP Spoofing

### Definition

**IP Spoofing** is a cyberattack technique in which an attacker forges or manipulates the source Internet Protocol (IP) address of a network packet to make it appear as though it originated from a trusted or legitimate device. By disguising their real IP address, attackers can hide their identity, bypass IP-based security measures, and facilitate attacks such as Denial-of-Service (DoS), Distributed Denial-of-Service (DDoS), and session hijacking.

### How the Attack Works

An IP Spoofing attack works by forging the source IP address of a network packet to make it appear as though it originates from a trusted or legitimate device. The attacker sends packets with a fake IP address instead of their real one, making it difficult for the target system to identify the true source of the traffic.

**The attack typically works as follows**:

 The attacker creates network packets with a forged (spoofed) source IP address.
 These packets are sent to the target server or network.
 The target system believes the packets came from a trusted device because of the fake IP address.
 The attacker uses the spoofed packets to bypass IP-based security measures, hide their identity, or launch attacks such as DoS, DDoS, or session hijacking.
 As a result, the target system may accept malicious traffic or become unable to identify the actual attacker.

### Real-World Example: GitHub DDoS Attack Using IP Spoofing (2018)

On February 28, 2018, GitHub was targeted by one of the largest Distributed Denial-of-Service (DDoS) attacks ever recorded at the time. The attackers exploited vulnerable Memcached servers and used **IP spoofing** to forge GitHub's IP address as the source of their requests. As a result, the Memcached servers sent enormous amounts of response traffic to GitHub instead of the attackers.

The attack generated a peak traffic volume of approximately **1.35 terabits per second (Tbps)**, temporarily disrupting GitHub's services. GitHub quickly mitigated the attack by redirecting traffic through a DDoS protection provider, which filtered the malicious traffic and restored normal operations within about 10 minutes.

This incident demonstrated how IP spoofing can be used to conceal an attacker's identity and amplify malicious traffic, making large-scale DDoS attacks more effective.

### Impact

IP Spoofing can have serious consequences for both individuals and organizations. The major impacts include:

**Conceals the Attacker's Identity:** By using a forged IP address, attackers can hide their real identity, making it difficult to trace the source of the attack.

**Facilitates DoS and DDoS Attacks:** IP spoofing is commonly used in Denial-of-Service (DoS) and Distributed Denial-of-Service (DDoS) attacks to overwhelm target systems with malicious traffic.

**Unauthorized Access:** Attackers may impersonate trusted devices to bypass IP-based authentication and gain unauthorized access to networks or systems.

**Session Hijacking:** IP spoofing can be used to take over active communication sessions, allowing attackers to intercept or manipulate sensitive information.

**Network Disruption:** Spoofed packets can consume network resources, degrade system performance, and interrupt normal business operations.

### Mitigation Strategies

The following measures can help prevent or reduce the risk of IP Spoofing attacks:

**Implement Ingress and Egress Filtering**
   Network routers should verify the source IP address of incoming and outgoing packets. Packets with forged or invalid source IP addresses should be blocked, preventing attackers from using spoofed IP addresses.

 **Use Packet Filtering Firewalls**
   Firewalls can inspect network traffic and filter packets with suspicious or unauthorized source IP addresses. This helps prevent spoofed packets from reaching internal systems.

**Use Authentication and Encryption Protocols**
   Implement secure protocols such as **IPsec**, **TLS**, and **VPNs** to authenticate communicating devices and encrypt data. These protocols help ensure that communication is between legitimate parties and reduce the risk of spoofing attacks.


-------------------------------------------------------------------------------
--------------------------------------------------------------------------------

### DNS Poisoning

### Definition

DNS Poisoning, also known as DNS Spoofing, is a cyberattack in which an attacker manipulates Domain Name System (DNS) records to redirect users from a legitimate website to a malicious or fraudulent website. By inserting false DNS information into a DNS cache or server, attackers can deceive users into visiting fake websites, where sensitive information such as usernames, passwords, and financial details can be stolen.

### How the Attack Works

A DNS Poisoning attack works by altering DNS records or inserting false information into a DNS cache. As a result, users are redirected to malicious websites instead of the legitimate websites they intended to visit.

The attack typically works as follows:

 A user enters the address of a legitimate website into their web browser.
 The DNS server receives the request to translate the domain name into an IP address.
 The attacker injects false DNS information into the DNS cache or compromises the DNS server. The DNS server returns the fake IP address instead of the correct one.
 The user is redirected to a malicious website without realizing it, where sensitive information may be stolen.

### Real-World Example: Kaminsky DNS Cache Poisoning Vulnerability (2008)

In 2008, security researcher Dan Kaminsky discovered a critical vulnerability in the Domain Name System (DNS) that made many DNS servers vulnerable to cache poisoning attacks. Attackers could inject false DNS records into a DNS resolver's cache, causing users to be redirected from legitimate websites to malicious websites without their knowledge.

The vulnerability affected a large number of DNS servers worldwide and posed a significant threat to internet security. Major software vendors, including Microsoft, Cisco, and ISC, quickly released security updates to fix the vulnerability before it could be widely exploited.                

### Impact

DNS Poisoning can have severe consequences for both users and organizations. The major impacts include:

**Redirection to Malicious Websites:** Users may unknowingly visit fake websites designed to steal sensitive information.

**Credential Theft:** Attackers can capture usernames, passwords, banking details, and other confidential information.

**Malware Distribution:** Malicious websites can install malware or ransomware on users' devices.

**Business Disruption:** Organizations may experience service interruptions, financial losses, and damage to their reputation.

**Loss of User Trust:** Customers may lose confidence in an organization's online services if they are redirected to fraudulent websites.

### Mitigation Strategies

The following measures can help prevent DNS Poisoning attacks:

**Implement DNSSEC (Domain Name System Security Extensions)**
   DNSSEC digitally signs DNS records, allowing users to verify that DNS responses are authentic and have not been altered.

**Use Secure and Trusted DNS Servers**
   Configure systems to use trusted DNS providers and keep DNS servers updated with the latest security patches to reduce vulnerabilities.

**Regularly Clear DNS Cache and Monitor DNS Activity**
    Clearing cached DNS records and continuously monitoring DNS traffic can help detect suspicious changes and reduce the risk of cache poisoning.

## Comparison of Common Network Security Threats

| Threat | Attack Vector | Who is at Risk | Difficulty to Execute | Ease of Mitigation |
|---------|---------------|----------------|-----------------------|--------------------|
| **DoS (Denial-of-Service)** | A single attacker floods a target server or network with excessive requests. | Small businesses, websites, and online services. | Medium | Moderate – Firewalls, rate limiting, and traffic monitoring can reduce the risk. |
| **DDoS (Distributed Denial-of-Service)** | Multiple compromised devices (botnets) flood the target with malicious traffic. | Large organizations, cloud providers, financial institutions, and e-commerce platforms. | High | Moderate to Difficult – Requires DDoS protection services, CDNs, and traffic filtering. |
| **Man-in-the-Middle (MITM)** | Intercepts communication between two parties to steal or modify data. | Public Wi-Fi users, online banking users, businesses, and organizations. | Medium | Easy to Moderate – HTTPS, VPNs, SSL/TLS encryption, and MFA provide strong protection. |
| **IP Spoofing** | Uses a forged IP address to impersonate a trusted device or hide the attacker's identity. | Enterprise networks, servers, and organizations using IP-based authentication. | High | Moderate – Ingress/egress filtering, firewalls, and IPsec help prevent spoofing. |
| **DNS Poisoning / DNS Spoofing** | Alters DNS records or cache to redirect users to malicious websites. | Internet users, businesses, DNS providers, and government organizations. | High | Moderate – DNSSEC, secure DNS servers, and regular patching reduce the risk. |


## Conclusion

Network security threats such as DoS, DDoS, Man-in-the-Middle (MITM), IP Spoofing, and DNS Poisoning continue to pose significant risks to individuals and organizations. These attacks can disrupt services, compromise sensitive information, and cause financial and reputational damage. Understanding how these threats work and implementing appropriate security measures are essential for maintaining a secure network environment.

### Key Takeaways for a Network Administrator

1. Implement layered security controls such as firewalls, intrusion detection systems (IDS), encryption, and Multi-Factor Authentication (MFA) to protect network resources.

2. Continuously monitor network traffic, apply software updates, and patch vulnerabilities to detect and prevent cyberattacks at an early stage.

3. Educate users about cybersecurity best practices, including recognizing phishing attempts, avoiding unsecured public Wi-Fi networks, and using strong passwords and secure authentication methods.

 ## References

1. National Institute of Standards and Technology (NIST). https://www.nist.gov

2. Cybersecurity and Infrastructure Security Agency (CISA). https://www.cisa.gov

3. MITRE ATT&CK Framework. https://attack.mitre.org

4. Cloudflare Learning Center. https://www.cloudflare.com/learning/

5. SANS Institute Reading Room. https://www.sans.org/white-papers/

6. GitHub Engineering Blog – DDoS Incident Report (2018). https://github.blog/news-insights/github/ddos-incident-report/

7. Lenovo Security Advisory – Superfish Vulnerability. https://support.lenovo.com/us/en/product_security/superfish

8. IBM – Man-in-the-Middle Attack. https://www.ibm.com/think/topics/man-in-the-middle-attack