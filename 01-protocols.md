# 📡 Protocols

[← Back to Home](./README.md)

**Protocols** are standardized sets of rules and conventions that govern how devices communicate and exchange data over a network. They define *how* data should be formatted, transmitted, received, and interpreted across different devices to ensure effective and reliable communication.

| Protocol Type | Role | Examples |
|---|---|---|
| Network | Addressing & Routing | IP, ARP, ICMP |
| Transport | Reliable/Fast Delivery | TCP, UDP |
| Application | End-user Services | HTTP, SNMP, SSL |

---

## ARP (Address Resolution Protocol)

ARP is used to find the physical hardware address (MAC address) that corresponds to a given IPv4 address.

- **Why it's needed:** IP addresses are 32 bits; MAC addresses are 48 bits — ARP bridges the gap.
- **How it works:** A device broadcasts "Who has this IP?" and the matching device replies with its MAC address.
- **OSI Layer:** Operates between Layer 2 (Data Link) and Layer 3 (Network).
- **Packet types:** Request (opcode 1) and Reply (opcode 2), carried in Ethernet frames with EtherType `0x0806`.

> ARP is crucial for local network communication, bridging IP addressing (routing) with MAC addressing (hardware delivery).

---

## TCP (Transmission Control Protocol)

A core transport layer (Layer 4) protocol enabling reliable, ordered, and error-checked delivery of data between devices over IP.

| Feature | Description |
|---|---|
| Connection-oriented | 3-way handshake: SYN → SYN-ACK → ACK |
| Reliable delivery | Sequence numbers, ACKs, retransmission of lost packets |
| Flow control | Manages transmission rate based on receiver capacity |
| Congestion control | Slow Start and Congestion Avoidance algorithms |
| Connection termination | 4-step handshake: FIN → ACK → FIN → ACK |

**Common uses:** HTTP/HTTPS, SMTP, IMAP, FTP, SSH, Telnet

---

## UDP (User Datagram Protocol)

A connectionless, lightweight transport layer protocol that sends data quickly without establishing a formal connection.

| Feature | Description |
|---|---|
| Connectionless | No handshake — low latency |
| Best-effort delivery | Packets may be lost, duplicated, or arrive out of order |
| Stateless | No state maintained between sender/receiver |
| Simple header | Fixed 8-byte header |
| No flow/congestion control | Sends regardless of network conditions |
| Multicast/broadcast support | Can send to multiple recipients simultaneously |

**Common uses:** Online gaming, VoIP, video streaming, DNS lookups, IPTV

---

## IP (Internet Protocol)

Responsible for **addressing and routing data packets** across networks from source to destination.

- Assigns unique IP addresses to every network device.
- Divides data into **packets**, each carrying source and destination IP headers.
- Is **connectionless and stateless** — each packet routes independently.
- Works with TCP and UDP to ensure efficient and reliable transmission.

| Version | Bit Length | Example |
|---|---|---|
| IPv4 | 32-bit | `192.168.1.1` |
| IPv6 | 128-bit | `2001:0db8::1` |

---

## HTTP (Hypertext Transfer Protocol)

An application-layer protocol for transferring data (mainly webpages) over the World Wide Web.

- **Client-server:** Client sends a request; server returns a response.
- **Stateless:** Each request is independent (cookies enable session management).
- **Methods:** GET, POST, PUT, DELETE, etc.

**Evolution:** HTTP/0.9 → HTTP/1.0 → HTTP/1.1 → HTTP/2 → HTTP/3 (QUIC-based)

---

## SNMP (Simple Network Management Protocol)

An application-layer protocol for monitoring, managing, and configuring network devices (routers, switches, servers, printers, etc.).

| Component | Role |
|---|---|
| SNMP Manager (NMS) | Central system that monitors/controls devices |
| SNMP Agent | Software on managed devices that responds to queries |
| MIB (Management Information Base) | Hierarchical database of device variables |

**UDP ports:** 161 (requests) / 162 (traps/notifications)

| Version | Security |
|---|---|
| SNMPv1 / v2c | Limited — community-string access control |
| SNMPv3 | Authentication, encryption, and access control |

---

## ICMP (Internet Control Message Protocol)

A network layer protocol used to send error messages and operational information about data delivery.

- Reports errors: destination unreachable, TTL expired, service unavailable.
- Powers diagnostics: **ping** (echo request/reply) and **traceroute** (time exceeded messages).
- NOT used for application data exchange — only for control messages.
- Protocol number `1` in the IP header.

---

## SSL (Secure Sockets Layer)

A protocol developed to secure communications between web clients and servers by encrypting transmitted data.

**Handshake process:**
1. Browser requests the server's SSL certificate and public key.
2. Browser verifies the certificate against trusted authorities.
3. Both parties agree on encryption algorithms and generate a shared symmetric session key.
4. All subsequent data is encrypted.

- Provides **privacy**, **authentication**, and **data integrity**.
- Websites using SSL/TLS show **HTTPS** and a padlock icon.
- SSL has been largely replaced by **TLS (Transport Layer Security)**, though the term "SSL" is still widely used.
