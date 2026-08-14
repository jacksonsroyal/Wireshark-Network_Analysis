\# Network Traffic Analysis Findings



\## Project Summary



This project involved capturing and analyzing live network traffic using Wireshark. The objective was to identify common protocols used during normal web browsing and understand how devices establish secure network connections.



\---



\## Environment



\- Operating System: Windows 11

\- Tool: Wireshark 4.x

\- Capture Driver: Npcap

\- Network Type: Home Wi-Fi



\---



\# Finding 1: DNS Query



\*\*Protocol:\*\* DNS



A DNS query was captured while accessing `www.google.com`. This packet shows the client requesting the IP address associated with the domain name.



\*\*Why it matters\*\*



DNS is responsible for translating domain names into IP addresses so devices can locate services on a network.



\---



\# Finding 2: DNS Response



\*\*Protocol:\*\* DNS



The DNS server responded with multiple IPv4 addresses for `www.google.com`.



\*\*Observation\*\*



Google returns multiple IP addresses for redundancy and load balancing.



\---



\# Finding 3: TLS Client Hello



\*\*Protocol:\*\* TLS



A TLS Client Hello packet was captured during the establishment of a secure HTTPS connection.



The packet included:



\- TLS Version

\- Cipher Suites

\- Supported Groups

\- Server Name Indication (SNI)

\- JA3 Fingerprint



\*\*Why it matters\*\*



The Client Hello is the first step in negotiating an encrypted connection between a client and a server.



\---



\# Finding 4: TCP SYN Packet



\*\*Protocol:\*\* TCP



A TCP SYN packet was captured while initiating an HTTPS connection.



\*\*Observation\*\*



The SYN packet begins the TCP three-way handshake used to establish a reliable connection before application data is transmitted.



\---



\# Key Skills Demonstrated



\- Packet Analysis

\- DNS Investigation

\- TCP/IP Fundamentals

\- TLS Handshake Analysis

\- Network Troubleshooting

\- Security Documentation

\- Wireshark Packet Inspection



\---


## Lessons Learned



\- Learned how to filter traffic using Wireshark display filters.

\- Identified the role of DNS in name resolution.

\- Examined the TCP three-way handshake used to establish reliable connections.

\- Observed how TLS negotiates encryption before transmitting application data.

\- Improved familiarity with packet structure and protocol analysis.



\---



\# Conclusion



This lab demonstrates a practical understanding of how modern network communications function. Capturing and analyzing DNS, TCP, and TLS traffic provides foundational knowledge required for Security Operations Center (SOC) analysis, incident response, and network troubleshooting.

