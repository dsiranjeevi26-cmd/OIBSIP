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

3. Installed Npcap when prompted. Npcap is required to capture network packets on Windows.

4. Completed the installation and launched Wireshark.

### Permissions Required

Wireshark requires permission to access the network interface.

- On Windows, packet capturing may require **Administrator privileges**.
- Npcap must be installed and enabled during setup.

---

# Capturing Live Network Traffic

1. Opened Wireshark.
2. Selected the active Ethernet network interface.
3. Started packet capture.
4. Browsed several websites to generate network traffic.
5. Continued capturing traffic for **more than 2 minutes**.
6. Stopped the capture.
7. Saved the capture file as:

```
wireshark_capture.pcap
```

---

# HTTP Display Filter

### Filter Used

```
http
```

### Observation

The HTTP filter displayed unencrypted HTTP requests and responses.

Captured packets included:

- GET / HTTP/1.1
- HTTP/1.1 200 OK
- HTTP/1.1 301 Moved Permanently

---

# DNS Display Filter

### Filter Used

```
dns
```

### Observation

The DNS filter displayed DNS queries and responses.

Observed:

- Standard DNS Query
- Standard DNS Response
- Domain name resolution

Example domains observed:

- chatgpt.com
- googleapis.com
- neverssl.com

---

# TCP Display Filter

### Filter Used

```
tcp
```

### TCP Three-Way Handshake Analysis

A TCP connection is established using three packets.

### Step 1 – SYN

The client sends a SYN packet requesting a connection.

Packet Number: 11261

```
<Replace with your SYN packet numbe
```

---

### Step 2 – SYN-ACK

The server replies with a SYN-ACK packet acknowledging the request.

Packet Number:

```
<Replace with your SYN-ACK packet number>
```

---

### Step 3 – ACK

The client sends an ACK packet confirming the connection.

Packet Number:

```
<Replace with your ACK packet number>
```

The TCP connection is successfully established after the three-way handshake.

---

# Exported Capture File

The captured network traffic was exported as:

```
wireshark_capture.pcap
```

The file is included in this GitHub repository.

---

# Unencrypted HTTP Packet Analysis

An unencrypted HTTP GET request was captured.

### Packet Information

| Field | Value |
|-------|-------|
| Protocol | HTTP |
| Method | GET |
| Request | GET / HTTP/1.1 |
| Host | neverssl.com |
| Source Port | 32459 |
| Destination Port | 80 |
| Destination IP | 34.223.124.45 |

---

## Information Visible

The following information was visible in plain text:

- HTTP Method (GET)
- Requested Resource (/)
- Host Name (neverssl.com)
- Browser User-Agent
- Connection Header
- Accept Header

Because HTTP does not encrypt data, anyone monitoring the network can read this information.

---

# Why Unencrypted HTTP Traffic Is Dangerous

HTTP sends data in plain text.

Anyone connected to the same network can capture packets using tools such as Wireshark and view transmitted information.

Risks include:

- Password theft
- Username theft
- Session hijacking
- Information disclosure
- Man-in-the-Middle attacks

---

# How HTTPS Prevents Eavesdropping

HTTPS uses TLS (Transport Layer Security) to encrypt communication between the client and the web server.

Benefits include:

- Encrypts transmitted data
- Prevents packet sniffing
- Protects sensitive information
- Verifies the identity of the server
- Protects data integrity

Even if packets are captured, their contents cannot be read because they are encrypted.

---

# Security Observations

During packet analysis, the following protocols were observed:

- TCP
- HTTP
- DNS
- TLSv1.2
- TLSv1.3
- ARP

HTTP traffic was readable because it was unencrypted, while HTTPS traffic appeared encrypted.

---

# Glossary

## Packet

A packet is a small unit of data transmitted across a network.

---

## Protocol

A protocol is a set of rules that allows devices to communicate over a network.

Examples include TCP, HTTP, DNS, and HTTPS.

---

## Port

A port is a numbered communication endpoint used by network services.

Examples:

- Port 80 – HTTP
- Port 443 – HTTPS
- Port 53 – DNS

---

## Payload

The payload is the actual information or data carried inside a packet.

---

## Handshake

A handshake is the process used to establish a communication session before data transfer begins.

TCP uses a three-way handshake consisting of SYN, SYN-ACK, and ACK packets.
---

# Ethics Note

This packet capture was performed only on my own computer and network for educational purposes.

Traffic was captured only on a network that I own or have permission to analyse.

No unauthorized systems or public networks were monitored.

---

# Conclusion

This task provided practical experience with Wireshark and network traffic analysis. Live traffic was captured, filtered using HTTP, DNS, and TCP display filters, and analysed to understand how network communication works. An unencrypted HTTP GET request demonstrated how sensitive information can be exposed in plain text, while HTTPS encryption protects against eavesdropping. This exercise strengthened practical knowledge of packet analysis and secure network communication.

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
