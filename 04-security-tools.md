# 🛠️ Security Tools

[← Back to Home](./README.md)

---

## Burp Suite

**Burp Suite** is a comprehensive software platform for security testing of web applications, developed by PortSwigger. It is an essential tool for penetration testers, security researchers, and bug bounty hunters.

Burp Suite acts as an **intercepting proxy** — it sits between your browser and the web server, allowing you to capture, inspect, and modify HTTP(S) traffic in real time.

### Core Modules

| Module | Function |
|---|---|
| **Proxy** | Intercept and modify all browser-to-server traffic |
| **Scanner** | Automated vulnerability discovery (Professional/Enterprise editions) |
| **Repeater** | Manually resend and tweak HTTP requests to test behavior |
| **Intruder** | Automated customizable attacks (fuzzing, brute force) |
| **Decoder** | Encode/decode data in various formats (Base64, URL, hex, etc.) |
| **Comparer** | Diff tool to spot differences between two responses |
| **Sequencer** | Analyze randomness of session tokens |

### Editions

| Edition | Features |
|---|---|
| **Community** | Free — manual tools, limited scanner |
| **Professional** | Full automated scanner, all modules |
| **Enterprise** | CI/CD pipeline integration, automated scanning at scale |

### Common Use Cases
- Intercepting login requests to analyze authentication flows.
- Testing for SQL injection, XSS, CSRF in web forms.
- Replaying requests with modified parameters in Repeater.
- Fuzzing input fields to discover unexpected behavior.

---

## Metasploit

**Metasploit** is a powerful open-source framework for penetration testing and vulnerability assessment, developed by Rapid7. It provides security professionals and ethical hackers with a modular platform to discover, exploit, and validate vulnerabilities in a controlled, legal environment.

Metasploit functions as an **exploitation framework** — it combines *exploits* (code that targets a specific vulnerability) with *payloads* (actions performed once access is gained, like establishing a remote shell).

### Core Components

| Component | Description |
|---|---|
| **Exploits** | Code that takes advantage of a specific vulnerability |
| **Payloads** | What runs on the target after exploitation (e.g., Meterpreter shell) |
| **Auxiliary** | Scanners, fuzzers, and information gathering modules |
| **Post** | Post-exploitation modules (privilege escalation, pivoting, data collection) |
| **Encoders** | Obfuscate payloads to evade detection |
| **NOPs** | No-operation sleds used in exploit development |

### Use Cases

| Use Case | Description |
|---|---|
| Penetration Testing | Find and exploit security flaws to assess risk |
| Vulnerability Validation | Confirm vulnerabilities found by scanners (Nmap, Nessus) |
| Exploit Development | Build and test custom exploit code |
| Post-Exploitation | Privilege escalation, password extraction, data exfiltration |
| Automation | Automate scanning, brute force, and report generation |
| Integration | Works with Nmap, Nessus, and other security tools |
| Security Awareness | Demonstrate real vulnerability impacts to stakeholders |

### Common Interfaces

- **`msfconsole`** — The primary command-line interface.
- **`msfvenom`** — Payload generation and encoding tool.
- **Armitage** — Graphical UI built on top of Metasploit.
