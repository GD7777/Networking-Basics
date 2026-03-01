# 🔒 Securing a Network

[← Back to Home](./README.md)

> Securing a network involves implementing a combination of technical controls, policies, and best practices designed to prevent unauthorized access, detect threats, and protect data, systems, and services from compromise.

---

## Key Techniques

### 1. Defense in Depth

Layer multiple security controls across endpoints, servers, applications, and the network itself (L3–L7). No single control is sufficient — overlapping layers ensure that if one fails, others still protect the system.

**Examples:** Firewalls + IDS/IPS + endpoint AV + MFA + encryption + monitoring.

---

### 2. Network Segmentation

Divide your network into secure zones based on business function, sensitivity, or risk. Limit the blast radius if one segment is compromised.

**Examples:** Separate VLANs for HR, Finance, IT, and Guest Wi-Fi. DMZ for public-facing servers.

---

### 3. Least Privilege Access Control

Apply the principle of least privilege — users, services, and devices only have access to what they strictly need. Regularly review and revoke unnecessary permissions.

**Examples:** A web app's database account should only have SELECT/INSERT — not DROP TABLE. Developers shouldn't have prod access by default.

---

### 4. Strong Authentication and Authorization

Deploy strong password policies and enable multi-factor authentication (MFA) for remote access, critical resources, and admin accounts.

**Best practices:**
- Enforce password length and complexity requirements.
- Require MFA for all VPN, SSH, and admin logins.
- Use SSO with a centralized identity provider (IdP).
- Implement role-based access control (RBAC).

---

### 5. Firewalls and Access Control Lists (ACLs)

Enforce stateful inspection of network traffic to block malicious inbound and outbound traffic. Use ACLs to restrict which IPs and ports can communicate.

**Examples:** Block all inbound traffic except ports 80/443 on the web server. Deny outbound connections to known malicious IP ranges.

---

### 6. Continuous Monitoring and Incident Detection

Deploy network monitoring with IDS/IPS, SIEM, and log analysis tools to detect anomalies, attacks, or policy violations in real time.

**Tools:** Splunk, Elastic SIEM, Suricata, Snort, CrowdStrike, Darktrace.

---

### 7. User Training and Security Awareness

Conduct regular security awareness training for all users on phishing, social engineering, and safe computing practices. Humans are often the weakest link.

**Best practices:**
- Run simulated phishing campaigns.
- Train staff to recognize suspicious emails and links.
- Establish a clear process for reporting suspicious activity.

---

### 8. Backup and Disaster Recovery

Regularly back up critical data, configurations, and system images. Test your recovery process — a backup you've never restored is not a real backup.

**Best practices:**
- Follow the **3-2-1 rule**: 3 copies, 2 different media, 1 offsite.
- Encrypt backups at rest and in transit.
- Test restoration procedures regularly.
- Define RTO (Recovery Time Objective) and RPO (Recovery Point Objective).

---

## Summary Checklist

| Control | Status |
|---|---|
| Multi-layer security controls (Defense in Depth) | ☐ |
| Network segmentation / VLANs | ☐ |
| Least privilege access enforced | ☐ |
| MFA enabled for all critical access | ☐ |
| Firewalls and ACLs configured | ☐ |
| SIEM / IDS / IPS deployed | ☐ |
| Security awareness training completed | ☐ |
| Backup and DR plan tested | ☐ |
