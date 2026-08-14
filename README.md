# Wireshark Network Analysis Lab

## Overview

This project demonstrates the use of **Wireshark** to capture and analyze live network traffic generated during normal web browsing. The goal was to understand how common networking protocols interact to establish secure communications over the internet.

The packet capture focuses on three fundamental protocols:

- DNS (Domain Name System)
- TCP (Transmission Control Protocol)
- TLS (Transport Layer Security)

Throughout the lab, packet filtering and protocol inspection were used to examine the complete process of establishing a secure HTTPS connection.

---

## Objectives

- Capture live network traffic using Wireshark
- Analyze DNS name resolution
- Observe the TCP three-way handshake
- Inspect the TLS Client Hello handshake
- Practice Wireshark filtering techniques
- Document observations and findings

---

## Technologies Used

- Wireshark
- Windows 11
- TCP/IP
- DNS
- TLS 1.2
- HTTPS
- Git
- GitHub

---

## Project Structure

```
Wireshark-Network-Analysis/
│
├── README.md
├── Findings.md
├── Captures/
│   └── basic-network-capture.pcapng
│
└── Screenshots/
    ├── 01-dns-query.png
    ├── 02-dns-response-packet.png
    ├── 03-tls-client-hello.png
    └── 04-tcp-syn.png
```

---

## Network Traffic Analysis

### 1. DNS Query

The capture begins with a DNS request for **www.google.com**.

This packet asks the configured DNS server to translate the hostname into an IP address.

**Screenshot**

`Screenshots/01-dns-query.png`

---

### 2. DNS Response

The DNS server responds with multiple IPv4 (A) records.

Large services such as Google use multiple IP addresses to distribute traffic and improve availability.

**Screenshot**

`Screenshots/02-dns-response-packet.png`

---

### 3. TCP Connection

Before encrypted communication can begin, TCP establishes a reliable connection using the three-way handshake.

The captured SYN packet represents the first step of that process.

**Screenshot**

`Screenshots/04-tcp-syn.png`

---

### 4. TLS Handshake

Once TCP is established, the client initiates a TLS handshake by sending a Client Hello.

This packet advertises:

- Supported TLS versions
- Supported cipher suites
- Random session values
- Server Name Indication (SNI)
- Encryption capabilities

After the handshake completes, HTTPS traffic becomes encrypted.

**Screenshot**

`Screenshots/03-tls-client-hello.png`

---

## Wireshark Display Filters Used

| Purpose | Filter |
|----------|--------|
| DNS Traffic | `dns` |
| TCP SYN Packets | `tcp.flags.syn == 1` |
| TLS Client Hello | `tls.handshake.type == 1` |
| HTTPS Traffic | `tcp.port == 443` |

---

## Skills Demonstrated

- Packet capture and analysis
- DNS protocol analysis
- TCP handshake inspection
- TLS handshake inspection
- Network troubleshooting
- Protocol filtering
- Technical documentation
- GitHub project documentation

---

## Key Concepts Learned

- DNS translates hostnames into IP addresses.
- TCP establishes reliable communication using the three-way handshake.
- TLS negotiates encryption before application data is transmitted.
- HTTPS encrypts web traffic after the TLS handshake completes.
- Wireshark enables detailed inspection of packet headers and protocol behavior.

---

## Files Included

| File | Description |
|------|-------------|
| README.md | Project documentation |
| Findings.md | Detailed packet analysis and observations |
| basic-network-capture.pcapng | Captured network traffic |
| Screenshots/ | Supporting screenshots of packet analysis |

---

## Future Improvements

Planned enhancements include:

- Analyze HTTP traffic in a controlled lab environment
- Capture ICMP echo requests and replies
- Inspect ARP traffic
- Analyze DHCP communication
- Compare TLS 1.2 and TLS 1.3 handshakes
- Export protocol statistics from Wireshark
- Perform packet analysis using larger capture files

---

## Conclusion

This project demonstrates the process of capturing and analyzing real network traffic using Wireshark. By examining DNS, TCP, and TLS packets, the lab provides practical experience with the protocols that form the foundation of secure internet communication.

The project also reinforces packet analysis, protocol identification, and technical documentation skills that are directly applicable to cybersecurity, networking, and SOC analyst roles.
