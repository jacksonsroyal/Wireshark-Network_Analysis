\# Wireshark Network Traffic Analysis



\## Overview



This project demonstrates my ability to capture, inspect, and analyze network traffic using Wireshark.



The objective was to identify common network protocols, examine packet structures, and understand how network communication occurs between a client and remote servers.



\---



\## Objectives



\- Capture live network traffic

\- Analyze DNS requests and responses

\- Identify TCP three-way handshake packets

\- Examine TLS Client Hello messages

\- Document packet-level observations

\- Practice Wireshark filtering and protocol analysis



\---



\## Tools Used



\- Wireshark

\- Npcap

\- Windows 11



\---



\## Protocols Analyzed



\- DNS

\- TCP

\- TLS

\- HTTPS

\- IPv4

\- Ethernet II



\---



\## Packet Filters Used



```text

dns

tcp.flags.syn == 1

tls.handshake.type == 1

tcp.port == 443

```



\---



\## Screenshots



\### DNS Query



!\[DNS Query](Screenshots/dns-query.png)



\---



\### DNS Response



!\[DNS Response](Screenshots/dns-response-packet.png)



\---



\### TCP SYN Packet



!\[TCP SYN](Screenshots/06-tcp-syn.png)



\---



\### TLS Client Hello



!\[TLS Client Hello](Screenshots/05-tls-client-hello.png)



\---



\## Key Findings



\- DNS resolved \*\*www.google.com\*\* into multiple IPv4 addresses.

\- TCP established communication using the SYN handshake.

\- HTTPS traffic was encrypted using TLS.

\- TLS Client Hello advertised supported cipher suites and TLS versions.

\- Application data remained encrypted after the TLS handshake.



A complete technical analysis is available in \*\*Findings.md\*\*.



\---



\## Skills Demonstrated



\- Packet Capture

\- Network Protocol Analysis

\- DNS Investigation

\- TCP Analysis

\- TLS Inspection

\- Wireshark Filters

\- Documentation

\- Network Troubleshooting



\---



\## Repository Structure



```text

Wireshark-Network-Analysis/

│

├── README.md

├── Findings.md

├── Captures/

│   └── basic-network-capture.pcapng

└── Screenshots/

&#x20;   ├── dns-query.png

&#x20;   ├── dns-response-packet.png

&#x20;   ├── 06-tcp-syn.png

&#x20;   └── 05-tls-client-hello.png

```



\---



\## What I Learned



This project strengthened my understanding of:



\- DNS name resolution

\- TCP connection establishment

\- TLS encryption

\- Packet inspection

\- Traffic filtering using Wireshark

\- Practical network troubleshooting



\---

