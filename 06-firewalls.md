# 🔥 Firewalls

[← Back to Home](./README.md)

A **firewall** is a security device — hardware, software, or a combination — that monitors, filters, and controls incoming and outgoing network traffic according to defined security rules. Firewalls serve as a barrier between trusted internal networks and untrusted external networks (such as the internet).

---

## Types of Firewalls

| Type | OSI Layer | Key Feature |
|---|---|---|
| Packet-Filtering | L3 / L4 | Stateless — filters by IP, port, protocol |
| Stateful Inspection | L3 / L4 | Tracks connection state |
| Proxy (App Gateway) | L7 | Intercepts traffic as a middleman |
| Next-Generation (NGFW) | L3 – L7 | Deep packet inspection, IPS, app awareness |
| Web Application (WAF) | L7 | Specialized for HTTP/HTTPS web traffic |

---

## 1. Packet-Filtering Firewalls

**How they work:** Inspect individual packets without tracking connection state. Allow or block based on IP addresses, ports, and protocols using predefined rules.

**Strengths:**
- Fast, simple, and resource-efficient.
- Good for blocking obvious unwanted traffic.

**Limitations:**
- Stateless — no awareness of packet context.
- Cannot detect sophisticated attacks or application-level threats.

**Example use case:** A basic router firewall blocks all incoming SSH and Telnet traffic except from specific internal addresses.

---

## 2. Stateful Inspection Firewalls

**How they work:** Track the "state" of active connections. Evaluate whether a packet is part of an established, authorized conversation — not just the headers.

**Strengths:**
- More secure than packet-filtering.
- Dynamically allow return traffic for trusted outgoing connections.

**Limitations:**
- Heavier on resources than stateless firewalls.
- Does not inspect traffic payload at the application level.

**Example use case:** Corporate firewalls allowing all outbound connections but only permitting inbound traffic that matches an active internal session.

---

## 3. Proxy Firewalls (Application-Level Gateways)

**How they work:** Operate at L7 — intercept and inspect all traffic as an intermediary (proxy) between users and services. Understand application-specific protocols (HTTP, FTP, etc.).

**Strengths:**
- Filter based on specific application commands or payload content.
- Protect internal systems by hiding them from direct exposure.

**Limitations:**
- Higher latency and resource requirements.
- May not support every application/protocol out of the box.

**Example use case:** A web proxy mediating all employee internet access, blocking malicious sites and dangerous file downloads.

---

## 4. Next-Generation Firewalls (NGFW)

**How they work:** Combine traditional firewall capabilities with deep packet inspection (DPI), intrusion prevention (IPS), application awareness, user identity control, and advanced threat detection. Operate from L3 to L7.

**Strengths:**
- Detect and block threats based on application behavior, user identity, or content matching.
- Integrate threat intelligence feeds and automated response.

**Limitations:**
- More expensive and complex to configure.
- Require regular updates to stay effective.

**Example use case:** Enterprises deploying NGFW at the network perimeter to block spam, malware, botnets, and enforce user-based policies for social media and cloud storage.

---

## 5. Web Application Firewalls (WAF)

**How they work:** Specifically designed to monitor, filter, and block HTTP(S) traffic to and from web applications. Detect and stop threats like SQL injection, XSS, and file inclusion attacks.

**Strengths:**
- Specialized for web-layer security threats.
- Works with complex and custom web application logic.

**Limitations:**
- Limited protection for non-web traffic.
- Can cause false positives that block legitimate activity if not properly tuned.

**Example use case:** E-commerce websites deploying WAF to stop attackers from exploiting web forms or APIs.

---

## Firewall Comparison

| Feature | Packet-Filter | Stateful | Proxy | NGFW | WAF |
|---|---|---|---|---|---|
| Speed | ✅ Very Fast | ✅ Fast | ⚠️ Slower | ⚠️ Moderate | ⚠️ Moderate |
| State tracking | ❌ | ✅ | ✅ | ✅ | ✅ |
| App-layer inspection | ❌ | ❌ | ✅ | ✅ | ✅ |
| IPS integration | ❌ | ❌ | ❌ | ✅ | ❌ |
| Web-specific protection | ❌ | ❌ | ⚠️ Limited | ⚠️ Partial | ✅ |
| Cost | 💲 Low | 💲💲 | 💲💲 | 💲💲💲 | 💲💲 |
