# 📊 SIEM

[← Back to Home](./README.md)

A **SIEM (Security Information and Event Management)** platform centralizes log collection, real-time monitoring, event correlation, and incident response to detect and investigate security threats across an organization.

> **SIM** (Security Information Management) = log collection + long-term storage  
> **SEM** (Security Event Management) = real-time monitoring + alerting  
> **SIEM** = both combined into one platform

---

## Core Capabilities

| Capability | Description |
|---|---|
| **Log aggregation** | Central collection and normalization of logs from all sources |
| **Real-time monitoring** | Continuous analysis of incoming security events |
| **Correlation and alerting** | Pattern identification indicating security incidents |
| **Incident investigation** | Searchable historical data and dashboards for forensics |
| **Compliance reporting** | Automated audit-ready reports (PCI DSS, ISO 27001, HIPAA, etc.) |

---

## Core Components

### 1. Log Sources & Collectors
Agents or agentless connectors deployed on endpoints, firewalls, IDS/IPS, databases, cloud services, and applications. They forward logs to the central SIEM platform.

### 2. Normalization & Parsing
Structuring raw logs (which may vary in format across vendors) into common, searchable fields such as: timestamp, source IP, destination IP, user, event type, and action.

### 3. Event Correlation Engine
Rule-based or statistical/ML engines that detect multi-step attacks or anomalies by connecting related events across different sources over time.

**Example:** Login failure from IP X → Port scan from IP X → Successful login = potential brute force + intrusion.

### 4. Storage & Indexing
High-performance, searchable datastore for large volumes of log data. Common backends include Elasticsearch and Splunk DB. Enables fast searches during incident response.

### 5. Dashboards & Reporting
Visual representations of security posture, event trends, alert volumes, and compliance metrics. Helps security teams understand the environment at a glance.

### 6. Incident Response Workflows
Case management, ticketing system integration (e.g., ServiceNow, Jira), and automated remediation playbooks (SOAR integration) to streamline response.

---

## Popular SIEM Platforms

| Platform | Type | Notes |
|---|---|---|
| **Splunk** | Commercial | Industry leader, highly flexible, expensive |
| **Microsoft Sentinel** | Cloud-native | Azure-integrated, pay-as-you-go |
| **IBM QRadar** | Commercial | Strong correlation engine |
| **Elastic SIEM** | Open-source / Commercial | Built on the ELK stack |
| **Wazuh** | Open-source | Great for smaller orgs, host-based |
| **Graylog** | Open-source / Commercial | Log management focus |

---

## SIEM Use Cases

- Detecting brute force attacks by correlating repeated failed login events.
- Identifying lateral movement by tracking unusual internal traffic patterns.
- Alerting on data exfiltration via large outbound data transfers.
- Compliance auditing for PCI DSS, HIPAA, or ISO 27001.
- Forensic investigation after a security incident using historical log data.

---

## SIEM vs. Related Tools

| Tool | Focus |
|---|---|
| **SIEM** | Collect, correlate, and alert on security events |
| **IDS/IPS** | Detect/block malicious network traffic in real time |
| **EDR** | Endpoint-level threat detection and response |
| **SOAR** | Automate and orchestrate incident response workflows |
| **XDR** | Extended detection across endpoints, network, cloud (unified) |
