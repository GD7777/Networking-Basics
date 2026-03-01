# 🧱 OSI Model

[← Back to Home](./README.md)

The **OSI (Open Systems Interconnection) Model** is a conceptual framework that standardizes how different computer systems communicate over a network, divided into 7 layers.

---

## The 7 Layers

| Layer | Name | Role | Real-World Example |
|---|---|---|---|
| 7 | **Application** | Network services to applications | Web browser loading a page via HTTP |
| 6 | **Presentation** | Data translation, encryption, compression | Decrypting HTTPS data for display |
| 5 | **Session** | Manage sessions between applications | Staying logged in without re-entering credentials |
| 4 | **Transport** | Reliable/ordered data delivery, segmentation | Ensuring all video chunks arrive and reassemble correctly |
| 3 | **Network** | Routing and logical addressing across networks | Router using IP addresses to forward a web request |
| 2 | **Data Link** | Node-to-node transfer, error correction | Network switch using MAC addresses to direct traffic |
| 1 | **Physical** | Transmit raw bits over physical medium | Ethernet cable carrying electrical pulses |

---

## Layer Details

### Layer 1 — Physical
**Role:** Handles the physical connection between devices — transmits raw bits (0s and 1s) over a medium (cables, radio waves).  
**Functions:** Bit transmission, cable type selection, signal generation.  
**Example:** The Ethernet cable or Wi-Fi signal carrying electrical/optical pulses between your computer and a router.

### Layer 2 — Data Link
**Role:** Provides node-to-node data transfer and handles error correction from the physical layer.  
**Functions:** Framing, MAC addressing, error detection/correction.  
**Example:** A network switch checking MAC addresses to decide which device to send your data to within a local network.

### Layer 3 — Network
**Role:** Moves data between devices on different networks (routing and addressing across the internet).  
**Functions:** Logical addressing (IP), routing, packet forwarding.  
**Example:** Your home router deciding how to send a web request to the right destination using IP addresses.

### Layer 4 — Transport
**Role:** Ensures complete and reliable data transfer, segmentation, and error recovery.  
**Functions:** Segmentation, error control, flow control, port-based addressing.  
**Example:** When watching a video online, this layer ensures all pieces arrive correctly and re-assembles them.

### Layer 5 — Session
**Role:** Manages sessions or connections between applications — creation, maintenance, and termination.  
**Functions:** Session establishment, synchronization (checkpoints), dialog control.  
**Example:** Logging into a website keeps your session alive so you don't re-enter credentials for every page.

### Layer 6 — Presentation
**Role:** Translates data between the application and the network — formats, encryption, and compression.  
**Functions:** Data translation, encryption/decryption, compression.  
**Example:** Opening a JPEG sent via email, or decrypting sensitive information for display.

### Layer 7 — Application
**Role:** Closest to the end-user — provides network services to applications.  
**Functions:** Application-specific communication (HTTP, SMTP, FTP, etc.).  
**Example:** Using a web browser to open a website or an email client to send messages.

---

## Protocols per Layer

| OSI Layer | Example Protocols |
|---|---|
| Layer 7 – Application | HTTP, HTTPS, FTP, SMTP, SNMP, DNS |
| Layer 6 – Presentation | SSL/TLS, JPEG, MPEG |
| Layer 5 – Session | NetBIOS, RPC, PPTP |
| Layer 4 – Transport | TCP, UDP |
| Layer 3 – Network | IP, ICMP, ARP, OSPF |
| Layer 2 – Data Link | Ethernet, Wi-Fi (802.11), MAC |
| Layer 1 – Physical | Cables, Radio waves, Fiber optic |

---

## OSI Model Attacks

| Layer | Attack Types | Prevention |
|---|---|---|
| L1 Physical | Sniffing, hardware tampering, jamming | Physical security, cable protection, environmental monitoring |
| L2 Data Link | MAC spoofing, ARP poisoning, MAC flooding, VLAN hopping | Port security, DAI, VLANs, 802.1X, MAC filtering, IDS |
| L3 Network | MitM, IP spoofing, routing poisoning, DDoS, ICMP flooding | Firewalls, ACLs, segmentation, encrypted VPNs, DDoS protection |
| L4 Transport | Port scanning, SYN flood, session hijacking | Close unused ports, firewalls, IDS/IPS, SYN cookies, TLS |
| L5 Session | Session hijacking, replay attacks, session fixation | Encrypted sessions, timeouts, secure cookie management |
| L6 Presentation | Phishing, malware injection, SSL stripping | Encryption, user training, certificate pinning, input validation |
| L7 Application | SQLi, XSS, RCE, buffer overflow, HTTP flood | Secure coding, WAFs, MFA, patching, security scans |

### Layer Attack Details

#### L1 — Physical
- **Sniffing/Eavesdropping:** Intercept raw data signals via physical access to cables or wireless signals.
- **Hardware Tampering:** Physically altering or sabotaging network devices.
- **Jamming:** Disrupting wireless signals to block legitimate communications.

#### L2 — Data Link
- **MAC Spoofing:** Forging MAC addresses to impersonate authorized devices.
- **ARP Spoofing/Poisoning:** Manipulating ARP tables to redirect traffic to the attacker.
- **MAC Flooding:** Overloading a switch with fake MAC addresses, forcing it into "hub mode."

#### L3 — Network
- **Man-in-the-Middle (MitM):** Intercepting and possibly altering packets.
- **IP Spoofing:** Forging the source IP address in packets.
- **Routing Table Poisoning:** Altering routing info to reroute or interrupt data.

#### L4 — Transport
- **Port Scanning:** Enumerating open/active ports to find vulnerabilities.
- **SYN Flood:** Sending repeated SYN requests to exhaust server resources (DoS).
- **Session Hijacking:** Taking over a user's session by predicting sequence numbers.

#### L5 — Session
- **Session Hijacking:** Intercepting/stealing sessions to take over authenticated communications.
- **Session Replay:** Repeating or delaying messages to trick the recipient.
- **Session Fixation:** Forcing a user's session ID for later attacker use.

#### L6 — Presentation
- **Phishing:** Deceiving users to obtain login info or inject malicious code.
- **Malware Injection:** Inserting malicious payloads or encoding exploits.
- **SSL Stripping:** Downgrading secure connections to make them vulnerable.

#### L7 — Application
- **Exploits:** Buffer overflows, logic flaws in software.
- **SQL Injection, XSS, Remote Code Execution.**
- **DoS/DDoS targeting application protocols** (HTTP flood, SMTP attacks).
