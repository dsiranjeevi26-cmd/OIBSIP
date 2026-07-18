# CyberSecurity-Task8-WiresharkTrafficCapture

## Objective

The objective of this task is to capture live network traffic using Wireshark, analyse different network protocols, identify unencrypted HTTP traffic, examine the TCP three-way handshake, and understand why encrypted communication using HTTPS is important for network security.

---

# Tools Used

- Wireshark
- Npcap
- Windows 11
- Mozilla Firefox
- Ethernet Network Interface

---

# Wireshark Installation

1. Downloaded Wireshark from the official website:
   https://www.wireshark.org/

2. Ran the Wireshark installer.

3. Installed Npcap during the installation process. Npcap is required for capturing network packets on Windows.

4. Completed the installation and launched Wireshark.

## Permissions Required

Wireshark requires permission to access the network interface.

- Packet capturing may require running Wireshark with **Administrator privileges**.
- Npcap must be installed and enabled during setup.

---

# Capturing Live Network Traffic

1. Opened Wireshark.
2. Selected the active Ethernet network interface.
3. Started packet capture.
4. Browsed multiple websites to generate network traffic.
5. Captured live network traffic for more than **2 minutes**.
6. Stopped the capture.
7. Exported the capture as:

```text
wireshark_capture.pcap
```

The capture file is included in this GitHub repository.

---

# HTTP Display Filter

## Filter Used

```text
http
```

## Observation

The HTTP display filter showed unencrypted HTTP requests and responses.

Captured packets included:

- GET / HTTP/1.1
- HTTP/1.1 200 OK
- HTTP/1.1 301 Moved Permanently

The corresponding screenshot is available in the **screenshots** folder.

---

# DNS Display Filter

## Filter Used

```text
dns
```

## Observation

The DNS display filter showed DNS queries and responses used to resolve domain names into IP addresses.

Observed:

- Standard DNS Query
- Standard DNS Response
- Domain Name Resolution

Example domains observed:

- chatgpt.com
- googleapis.com
- neverssl.com

The corresponding screenshot is available in the **screenshots** folder.

---

# TCP Display Filter

## Filter Used

```text
tcp
```

## TCP Three-Way Handshake Analysis

TCP establishes a reliable connection using a three-way handshake.

### Step 1 – SYN

The client sends a SYN packet requesting to establish a connection.

**Packet Number:** 11261

### Step 2 – SYN-ACK

The server replies with a SYN-ACK packet acknowledging the connection request.

**Packet Number:** 11263

### Step 3 – ACK

The client sends an ACK packet confirming the connection.

**Packet Number:** 11265

After these three packets, the TCP connection is successfully established and data transfer begins.

The corresponding screenshot is available in the **screenshots** folder.

---

# Exported Capture File

The captured network traffic was exported as:

```text
wireshark_capture.pcap
```

The `.pcap` file is included in this GitHub repository for verification and analysis.

---

# Unencrypted HTTP Packet Analysis

An unencrypted HTTP GET request was identified during packet analysis.

## Packet Information

| Field | Value |
|-------|-------|
| Protocol | HTTP |
| Method | GET |
| Request | GET / HTTP/1.1 |
| Host | neverssl.com |
| Source IP | 10.219.89.106 |
| Destination IP | 34.223.124.45 |
| Source Port | 32459 |
| Destination Port | 80 |

## Information Visible

The following information was visible in plain text:

- HTTP Method (GET)
- Requested Resource (/)
- Host Name (neverssl.com)
- Browser User-Agent
- Connection Header
- Accept Header

Because HTTP traffic is not encrypted, anyone monitoring the network can read this information.

---

# Why Unencrypted HTTP Traffic Is Dangerous

HTTP sends information in plain text without encryption.

An attacker connected to the same network can capture packets using tools such as Wireshark and read sensitive information.

Potential risks include:

- Username theft
- Password theft
- Session hijacking
- Information disclosure
- Man-in-the-Middle (MITM) attacks

---

# How HTTPS Prevents Eavesdropping

HTTPS uses TLS (Transport Layer Security) to encrypt communication between the client and the web server.

Benefits of HTTPS include:

- Encrypts transmitted data
- Prevents packet sniffing
- Protects sensitive information
- Verifies the identity of the server
- Protects data integrity

Even if packets are captured, the contents cannot be read without the encryption keys.

---

# Security Observations

During packet analysis, the following protocols were observed:

- TCP
- HTTP
- DNS
- TLSv1.2
- TLSv1.3
- ARP

The HTTP packet clearly demonstrated that web requests can be viewed in plain text when encryption is not used.

HTTPS traffic appeared encrypted and its contents could not be viewed.

---

# Glossary

## Packet

A packet is a small unit of data transmitted across a network.

## Protocol

A protocol is a set of communication rules that allows devices to exchange data over a network.

Examples include TCP, HTTP, DNS, and HTTPS.

## Port

A port is a numbered communication endpoint used by network services.

Examples:

- Port 80 – HTTP
- Port 443 – HTTPS
- Port 53 – DNS

## Payload

The payload is the actual data carried inside a network packet, such as an HTTP request or DNS response.

## Handshake

A handshake is the process used to establish communication between two devices before data transmission begins.

TCP uses a three-way handshake consisting of:

- SYN
- SYN-ACK
- ACK

---

# Files Included

```text
CyberSecurity-Task8-WiresharkTrafficCapture/
│
├── README.md
├── wireshark_capture.pcap
└── screenshots/
    ├── capture_started.png
    ├── dns_filter.png
    ├── http_get_request.png
    ├── tcp_three_way_handshake.png
    └── packet_details.png
```

---

# Ethics Note

This packet capture was performed only on my own computer and network for educational purposes.

Traffic was captured only on a network that I own or have explicit permission to analyse.

No unauthorized systems or public networks were monitored.

---

# Conclusion

This task provided practical experience in capturing and analysing live network traffic using Wireshark. Different protocols including TCP, DNS, HTTP, TLS, and ARP were analysed. An unencrypted HTTP GET request demonstrated how information can be exposed in plain text when HTTP is used. HTTPS protects communication by encrypting network traffic and preventing eavesdropping. This exercise strengthened my understanding of packet analysis and secure network communication.

---

# References

1. Wireshark Documentation  
   https://www.wireshark.org/docs/

2. NIST Computer Security Resource Center  
   https://csrc.nist.gov/

3. CISA Cybersecurity Resources  
   https://www.cisa.gov/

4. Mozilla Developer Network – HTTP Overview  
   https://developer.mozilla.org/en-US/docs/Web/HTTP
