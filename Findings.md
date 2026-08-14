# Findings

## Overview

This project analyzed live network traffic captured with Wireshark to better understand how common networking protocols communicate during normal web browsing. The analysis focused on DNS, TCP, and TLS traffic generated while visiting websites.

---

# DNS Analysis

### Objective

Identify how a domain name is translated into an IP address.

### Observation

A DNS query was captured requesting the IPv4 address for **www.google.com**.

The response contained multiple A records, each pointing to a different Google IP address.

### Explanation

DNS (Domain Name System) is responsible for converting human-readable domain names into IP addresses that computers use for communication.

Google returned several IP addresses because it uses load balancing and distributed infrastructure to improve performance and availability.

### Evidence

- DNS Standard Query
- Query Name: www.google.com
- DNS Response
- Multiple IPv4 (A) Records Returned

---

# TCP Analysis

### Objective

Observe the beginning of a TCP connection.

### Observation

A TCP SYN packet was captured from the client to the destination server.

### Explanation

The SYN packet is the first step of the TCP three-way handshake.

This handshake establishes a reliable connection before application data is exchanged.

The normal sequence is:

1. SYN
2. SYN-ACK
3. ACK

Once complete, the client and server can begin transmitting data reliably.

### Evidence

- TCP SYN Flag Set
- Destination Port: 443 (HTTPS)
- Source Port: Ephemeral Client Port

---

# TLS Analysis

### Objective

Examine the start of an encrypted HTTPS session.

### Observation

A TLS Client Hello packet was captured immediately after the TCP connection was established.

### Explanation

The Client Hello begins the TLS handshake by advertising:

- Supported TLS versions
- Supported cipher suites
- Random session value
- Server Name Indication (SNI)
- Additional TLS extensions

The server uses this information to negotiate encryption settings before secure communication begins.

After the handshake completes, application data becomes encrypted and is no longer readable in plaintext.

### Evidence

- TLS Client Hello
- TLS Version 1.2
- Multiple Cipher Suites
- Server Name Indication (SNI)

---

# Packet Flow Summary

The captured traffic followed the expected communication process for a secure HTTPS connection:

1. DNS resolved the domain name.
2. TCP established a reliable connection.
3. TLS negotiated encryption.
4. HTTPS application data was exchanged securely.

---

# Key Takeaways

- DNS translates domain names into IP addresses.
- TCP provides reliable communication through the three-way handshake.
- TLS encrypts data transmitted over HTTPS.
- Wireshark allows detailed inspection of network protocols and packet headers.
- Modern HTTPS traffic protects application data using encryption, limiting visibility after the TLS handshake.

---

# Skills Demonstrated

- Packet capture using Wireshark
- DNS traffic analysis
- TCP handshake analysis
- TLS handshake inspection
- Packet filtering
- Network protocol analysis
- Documentation of technical findings

---

# Conclusion

This lab demonstrated the complete process of establishing a secure HTTPS connection, beginning with DNS name resolution, followed by TCP session establishment and TLS encryption negotiation. The exercise strengthened practical skills in packet analysis and improved understanding of how common network protocols interact during normal web browsing.
