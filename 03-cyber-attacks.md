# 💀 Cyber Attacks

[← Back to Home](./README.md)

> A **cyber attack** is any deliberate attempt by malicious actors to breach the security of computer systems, networks, or devices — to steal, damage, disrupt, or gain unauthorized access to data, services, or infrastructure.

---

## Attack Overview

| # | Attack | Description |
|---|---|---|
| 1 | [Phishing](#1-phishing) | Fraudulent messages to steal credentials or install malware |
| 2 | [Malware Infection](#2-malware-infection) | Malicious software damaging/exploiting systems |
| 3 | [Lateral Movement](#3-lateral-movement) | Spreading within a network after initial compromise |
| 4 | [Brute Force](#4-brute-force) | Automated credential guessing |
| 5 | [Privilege Escalation](#5-privilege-escalation) | Gaining higher access rights than authorized |
| 6 | [Web Attacks](#6-web-attacks) | XSS, SQLi, CSRF exploiting web app flaws |
| 7 | [DNS Attacks](#7-dns-attacks) | Redirecting, poisoning, or overwhelming DNS |
| 8 | [Port Scanning](#8-port-scanning--network-scanning) | Enumerating open ports/services as a precursor to attacks |
| 9 | [Vulnerability Scanning](#9-vulnerability-scanning) | Automated probing for known vulnerabilities |
| 10 | [Botnet](#10-botnet) | Network of compromised devices used for attacks |
| 11 | [SQL Injection](#11-sql-injection-sqli) | Malicious SQL injected through input fields |
| 12 | [DDoS](#12-ddos-distributed-denial-of-service) | Flooding a target with traffic to knock it offline |

---

## 1. Phishing

Fraudulent messages (email, SMS, voice) that trick users into revealing credentials or installing malware — a psychological, social engineering attack.

**Targets:** Email clients, browsers, cloud storage, corporate workstations, mobile devices.  
**Data at risk:** Login credentials, banking/financial info, personal identification, corporate secrets.

**Security Controls (L3–L7):**

| Layer | Control |
|---|---|
| L3 | IP filtering/blacklists for known phishing sources, network segmentation |
| L4 | Anomaly-based intrusion prevention |
| L5 | Enforce SSL/TLS, suspicious session timeouts |
| L6 | Email content inspection, hygiene gateways |
| L7 | Anti-phishing gateways, MFA, DMARC/DKIM, real-time URL analysis, user education |

---

## 2. Malware Infection

Malicious software (viruses, trojans, worms, ransomware) designed to damage, disrupt, or exploit. Spread via malicious attachments, compromised websites, and removable media.

**Targets:** Browsers, email clients, operating systems, PCs, servers, mobile devices, IoT.  
**Data at risk:** Sensitive files, customer records, credentials — essentially everything.

**Security Controls (L3–L7):**

| Layer | Control |
|---|---|
| L3 | Firewall, block malicious IPs |
| L4 | Detect suspicious port/protocol usage, intrusion prevention |
| L5 | SSL/TLS encrypted sessions, session timeout for inactivity |
| L6 | Content inspection (blocking malicious file formats), SSL inspection |
| L7 | Endpoint/web app firewalls, sandboxing, anti-malware, secure email gateways, real-time threat feeds |

---

## 3. Lateral Movement

After initial compromise, attackers spread within a network — seeking credentials and high-value assets while evading detection.

**Targets:** File sharing services, Active Directory, remote desktop, database apps, domain controllers.  
**Data at risk:** Credentials, admin secrets, intellectual property, customer data.

**Security Controls (L3–L7):**

| Layer | Control |
|---|---|
| L3 | Network segmentation/microsegmentation, restrict broadcast domains |
| L4 | Granular port-based filtering, detect abnormal connections |
| L5 | Monitor for unusual session creation, limit concurrent sessions |
| L6 | Encryption between internal apps, content-based DLP |
| L7 | UEBA, Zero Trust NAC, privilege management, strong auth, audit system-to-system communication |

---

## 4. Brute Force

Automated attacks trying all possible credential combinations to guess passwords on web portals, VPNs, SSH, or RDP.

**Targets:** Web portals, VPNs, SSH/RDP services, email login forms, cloud portals.  
**Data at risk:** Credentials, session tokens.

**Security Controls (L3–L7):**

| Layer | Control |
|---|---|
| L3 | Block known brute-force IP ranges, geo-blocking |
| L4 | Rate-limit TCP/UDP connections, firewall port restrictions |
| L5 | Limit session duration/frequency, OTP/MFA on session creation |
| L6 | Alert on abnormal volume of failed logins |
| L7 | WAF with bot/burst login detection, CAPTCHA, account lockouts, MFA, password policies |

---

## 5. Privilege Escalation

Exploiting a flaw to gain higher access rights — either vertically (user → admin) or horizontally (user → another user account).

**Targets:** Operating systems, directory services (AD), application servers, cloud infrastructure.  
**Data at risk:** Access control lists, root/admin databases, sensitive configurations.

**Security Controls (L3–L7):**

| Layer | Control |
|---|---|
| L3/L4 | Restrict admin access to management networks only |
| L5 | Require re-authentication for privilege changes |
| L6 | Monitor/decrypt privilege elevation commands |
| L7 | Least privilege, audit privilege changes, restrict admin API calls, JIT access, app sandboxing |

---

## 6. Web Attacks

Exploiting flaws in web apps, browsers, or servers — XSS, SQLi, CSRF, file upload attacks — to hijack sessions, steal data, or deface content.

**Targets:** Websites, web/mobile apps, APIs, e-commerce platforms, web servers.  
**Data at risk:** User data, authentication tokens, cookies, database records.

**Security Controls (L3–L7):**

| Layer | Control |
|---|---|
| L3 | Allow only legitimate protocols/ports, block dark web IPs |
| L4 | Firewall DDoS/autoscaling based on connection rate |
| L5 | Secure session cookie handling, establish TLS |
| L6 | Scan for malicious payloads, monitor input/output encoding |
| L7 | WAF with SQLi/XSS signatures, Secure SDLC, API security/gateways, input validation, bot management |

---

## 7. DNS Attacks

Targeting the Domain Name System to redirect, poison, or overwhelm DNS infrastructure for data interception, service disruption, or traffic redirection.

**Targets:** DNS resolvers, web browsers, email servers, DNS servers, load balancers.  
**Data at risk:** DNS cache/records, domain-to-IP mappings.

**Security Controls (L3–L7):**

| Layer | Control |
|---|---|
| L3 | Block unsolicited inbound DNS traffic, DDoS filtering |
| L4 | Rate-limit UDP-based DNS floods |
| L5 | Ensure only trusted sessions exchange DNS updates |
| L6 | DNS content filtering, DNS-over-HTTPS (DoH), DNS-over-TLS (DoT) |
| L7 | DNSSEC validation, DNS anomaly detection, restrict dynamic updates, monitor DNS tunneling |

---

## 8. Port Scanning / Network Scanning

Enumerating open ports, services, and hosts to find weaknesses — a common precursor to cyberattacks.

> A **port** is an endpoint for communication between different applications and servers.

**Targets:** Firewalls, routers, endpoint devices.  
**Data exposed:** Network topology, services map.

**Security Controls (L3–L7):**

| Layer | Control |
|---|---|
| L3 | Traffic-rate thresholds, geo-blocking, honeypot monitoring |
| L4 | Connection thresholds, block unused ports |
| L5 | Require authentication for sensitive ports |
| L6 | Alert on payload abnormalities in initial probes |
| L7 | Track/log repeated access attempts, alert on enumeration activity |

---

## 9. Vulnerability Scanning

Automated tools probe protocols/services for known vulnerabilities and report findings — used before or during an attack.

**Targets:** All network-exposed assets.

**Security Controls (L3–L7):**

| Layer | Control |
|---|---|
| L3 | Detect/block scanner fingerprints, dynamically segment scanner traffic |
| L4 | Rate-limit known scanner ports, alert on unusual protocol mix |
| L5 | Alert on repeated or prolonged session initiation |
| L6 | Content filtering for suspicious probe responses, enforce TLS-only |
| L7 | DAST tools, WAF blocks known probing patterns, enforce known-good queries only |

---

## 10. Botnet

A network of compromised devices ("bots" or "zombies") infected with malware and remotely controlled by a cybercriminal (the "botmaster"). Used for DDoS, spamming, data theft, and credential harvesting.

**Systems at risk:** PCs, servers, IoT devices (cameras, routers, smart appliances), mobile phones, industrial control systems.

**Prevention:** Endpoint anti-malware, network traffic anomaly detection, blocking C2 (command-and-control) server IPs, patching IoT devices.

---

## 11. SQL Injection (SQLi)

Inserting malicious SQL statements through user input fields that the application executes on its backend database — potentially exposing, modifying, or deleting sensitive data.

**Targets:** Web applications with unvalidated SQL queries, mobile apps, APIs, database servers (MySQL, MSSQL, PostgreSQL, Oracle).  
**Data at risk:** User accounts, payment info, business logic data, configuration files, logs.

**Prevention:** Parameterized queries/prepared statements, input validation, WAF, least-privilege database accounts, regular code review.

---

## 12. DDoS (Distributed Denial of Service)

A coordinated assault where many compromised devices flood a target with overwhelming traffic or requests, disrupting or completely knocking out legitimate user access. Often uses botnets from distributed global sources.

**Targets:** Websites, APIs, online gaming, cloud apps, email servers, DNS servers, routers, firewalls.

**Prevention:** DDoS scrubbing/filtering services (Cloudflare, AWS Shield), rate limiting, anycast routing, traffic anomaly detection, over-provisioning bandwidth.
