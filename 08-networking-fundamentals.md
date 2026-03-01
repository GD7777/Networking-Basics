# 🖧 Networking Fundamentals

[← Back to Home](./README.md)

> A **network** is a collection of devices connected together so they can communicate and share resources.

---

## Network Devices

| Device | OSI Layer | Role |
|---|---|---|
| **Modem** | L1/L2 | Converts ISP signal (fiber/DSL/cable) to Ethernet — does NOT route traffic |
| **Router** | L3 | Connects multiple networks and decides best path using a routing table |
| **Switch** | L2 | Connects devices within the same network using a MAC address table |
| **Firewall** | L3–L7 | Monitors and controls traffic based on security rules |
| **Access Point (AP)** | L2 | Provides Wi-Fi access to devices |
| **Load Balancer** | L4/L7 | Distributes incoming traffic across multiple servers |

### Device Details

**Modem**
- Converts ISP signal (fiber / DSL / cable) into Ethernet.
- ISP signal ≠ computer signal — the modem bridges this gap.
- Does NOT route traffic intelligently.

**Router**
- Connects multiple networks and decides the best path.
- Handles LAN ↔ Internet communication.
- Uses a **routing table** to forward packets.

**Switch**
- Connects devices inside the same network.
- Uses a **MAC address table** to direct traffic to the correct device.
- Example: Office floor switch connecting PCs and printers.

---

## Network Topology

| Topology | Description | Use Case |
|---|---|---|
| **Star** | All devices connect to a central switch; switch controls traffic | Home Wi-Fi, offices, IT parks |
| **Mesh** | Every device connects to multiple others; supports dynamic routing | Internet backbone, data centers |
| **Tree** | Star networks connected hierarchically; structured management | Corporate offices |
| **Hybrid** | Combination of multiple topologies | Large enterprise networks |

---

## IP Addressing

An **IP address** is a unique number assigned to each device connected to a network (mobile, laptop, server, router).

| Version | Bit Length | Example |
|---|---|---|
| IPv4 | 32-bit | `192.168.1.1` |
| IPv6 | 128-bit | `2001:0db8:85a3::8a2e:0370:7334` |

### Private vs. Public IP

| Type | Description | Example |
|---|---|---|
| **Private IP** | Used inside home/organization — not accessible on the internet | `192.168.1.x` (your laptop, phone) |
| **Public IP** | Visible on the internet — assigned by ISP | Your router's external IP |

---

## Subnetting

**Subnetting** is the practice of dividing a large network into smaller, more manageable sub-networks.

### CIDR (Classless Inter-Domain Routing)

CIDR notation expresses both an IP address and its network prefix length:

```
/24  →  32 - 24 = 8 bits for hosts  →  2^8 = 256 IPs (254 usable)

Example — 192.168.1.0/24:
  Network address  →  192.168.1.0      (1 address)
  Usable hosts     →  192.168.1.1 – 192.168.1.254  (254 addresses)
  Broadcast        →  192.168.1.255    (1 address)
```

### Common Subnet Sizes

| CIDR | Subnet Mask | Usable Hosts |
|---|---|---|
| /30 | 255.255.255.252 | 2 |
| /29 | 255.255.255.248 | 6 |
| /28 | 255.255.255.240 | 14 |
| /27 | 255.255.255.224 | 30 |
| /26 | 255.255.255.192 | 62 |
| /25 | 255.255.255.128 | 126 |
| /24 | 255.255.255.0 | 254 |
| /16 | 255.255.0.0 | 65,534 |

> **Subnet Mask:** A way to express CIDR in dotted-decimal format — `255.255.255.0` is equivalent to `/24`.

---

## DNS

**DNS (Domain Name System)** converts human-readable domain names (e.g., `google.com`) into IP addresses that computers can route to.

### DNS Resolution Process

```
Browser → DNS Resolver → Root Server → TLD Server → Authoritative Server → IP returned
```

| Component | Role |
|---|---|
| **DNS Resolver** | First contact — usually your ISP or local network resolver |
| **Root Server** | Knows where TLD servers are (there are 13 sets of root servers globally) |
| **TLD Server** | Handles top-level domains: `.com`, `.org`, `.in`, `.net`, etc. |
| **Authoritative Server** | Returns the final, definitive IP address for the domain |

### Common DNS Record Types

| Record | Purpose | Example |
|---|---|---|
| **A** | Maps domain → IPv4 address | `google.com → 142.250.80.46` |
| **AAAA** | Maps domain → IPv6 address | `google.com → 2607:f8b0::...` |
| **CNAME** | Alias — maps domain → another domain | `www → example.com` |
| **MX** | Mail server for the domain | Points to Gmail servers |
| **TXT** | Arbitrary text — used for SPF, DKIM, verification | `v=spf1 include:_spf.google.com` |
| **NS** | Nameserver records | Points to authoritative DNS servers |
| **PTR** | Reverse DNS — IP → domain name | Used in email anti-spam |

---

## Ports

A **port** is a logical number that identifies a specific application or service on a device for network communication.

```
Client IP:RandomPort  →  Server IP:ServicePort
Server IP:ServicePort →  Client IP:SameRandomPort
```

### Port Ranges

| Range | Name | Description |
|---|---|---|
| 0 – 1023 | Well-Known Ports | Reserved for standard services (HTTP, SSH, DNS, etc.) |
| 1024 – 49151 | Registered Ports | Used by specific applications (MySQL, PostgreSQL, RDP) |
| 49152 – 65535 | Dynamic/Ephemeral | Temporarily assigned to clients during connections |

### Common Ports Reference

| Protocol / Service | Port | TCP/UDP | Purpose |
|---|---|---|---|
| **HTTPS** | 443 | TCP | Secure web browsing (SSL/TLS encrypted) |
| **HTTP** | 80 | TCP | Unsecured web traffic |
| **SSH** | 22 | TCP | Secure remote login to servers (Linux/Unix) |
| **SFTP** | 22 | TCP | Secure file transfer over SSH |
| **FTP** | 21 | TCP | File transfer (unsecured) |
| **FTP Data** | 20 | TCP | Actual file data transfer |
| **Telnet** | 23 | TCP | Remote login (unsecured, largely obsolete) |
| **SMTP** | 25 | TCP | Sending emails between mail servers |
| **SMTP (Secure)** | 465 / 587 | TCP | Encrypted email sending |
| **POP3** | 110 | TCP | Downloading emails |
| **POP3 Secure** | 995 | TCP | Secure email download |
| **IMAP** | 143 | TCP | Email access and sync |
| **IMAP Secure** | 993 | TCP | Secure email sync |
| **DNS** | 53 | UDP/TCP | Domain name to IP resolution |
| **DHCP** | 67, 68 | UDP | Automatic IP address assignment |
| **RDP** | 3389 | TCP | Remote Desktop access (Windows) |
| **SMB** | 445 | TCP | File and printer sharing (Windows) |
| **SNMP** | 161 / 162 | UDP | Network monitoring and management |
| **NTP** | 123 | UDP | Time synchronization |
| **MySQL** | 3306 | TCP | Database communication |
| **PostgreSQL** | 5432 | TCP | Database communication |

### What does "port blocked" mean?

A **firewall** (host or network) is configured to:
- **Drop** packets — silently ignore them (no response sent to sender).
- **Reject** packets — explicitly deny and notify the sender.
