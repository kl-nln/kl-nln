# Hi, I'm Kiante 👋

I'm a cybersecurity professional and IT consultant transitioning into Cloud Security Engineering. I hold CompTIA Security+ and have spent the last several months building hands-on experience through homelab environments, security automation tools, and real-world client IT work across healthcare and transport industries.

Currently targeting **Security Analyst** and **SOC Analyst** roles while building toward **Cloud Security Engineer** and **AI Security Specialist** long term.

---

## 🏅 Certifications

| Certification | Issuer | Date Earned |
|---|---|---|
| CompTIA Security+ (SY0-701) | CompTIA | April 2026 |
| Google AI Essentials | Google | April 2026 |
| Google Prompting Essentials | Google | April 2026 |

> 🔄 In progress: AWS Certified Cloud Practitioner (Target: July 2026)

---

## 🔐 Featured Projects

### 🐍 [AD IAM Auditor — Python Security Tool](https://github.com/CodeBroKinty/ad-iam-auditor)
A modular Python tool that connects live to Active Directory via LDAPS and runs 4 automated IAM security checks, generating professional timestamped PDF and HTML audit reports.

**4 Automated Audit Checks:**
| Check | Severity |
|---|---|
| Cross-department group memberships | High |
| Disabled accounts in active OUs | Medium |
| Accounts with no group memberships | Medium |
| Inactive / never logged-in accounts (90+ day threshold) | High |

**Live audit results against corp.local:** 14 users scanned · 2 cross-department violations (Critical/High) · 2 disabled accounts in active OUs · 10 inactive accounts

**Key technical challenges solved:**
- LDAP signing enforcement (Windows Server 2025 `strongerAuthRequired`) — solved via LDAPS over port 636
- LDAPS certificate binding to NTDS registry store (`HKLM\SOFTWARE\Microsoft\Cryptography\Services\NTDS\SystemCertificates`)
- Python 3.14 MD4 removal breaking ldap3 NTLM auth — fixed via pycryptodome
- VirtualBox Host-Only network adapter configuration for WSL2 → VM communication

**Stack:** Python 3.14 · ldap3 · reportlab · jinja2 · pycryptodome · LDAPS · TLS · WSL2 · Windows Server 2025

---

### 🦈 [Wireshark Network Traffic Analysis Lab](https://github.com/CodeBroKinty/wireshark-lab)
Performed live packet capture, traffic baselining, and SOC-style forensic triage of a real-world NetSupport Manager RAT infection using Wireshark 4.4.14 on Parrot OS.

- Captured live traffic on `enp0s3`, analyzed protocol hierarchy (TCP 97.6%, TLS 10.1%, DNS 1%, ICMP 0.7%, ARP 0.1%)
- Applied 7 display filters — identified 2,012 SYN packets from Nmap scan, 125 RST rejections, DNS queries, and plaintext HTTP exposure via TCP stream follow
- Independently identified all **5 victim IOCs** before checking answers: IP address, MAC address, Windows hostname, AD username, and full name via NBNS, Kerberos, and SAMR protocol analysis
- Produced a professional SOC-style incident report documenting C2 beaconing to `45.131.214.85` over TCP 443

**Skills:** Wireshark · Packet Analysis · Network Forensics · TCP/IP · DNS · Kerberos · NBNS · SAMR · Nmap · Parrot OS · Linux · Incident Response · IOC Extraction · C2 Traffic Detection · Display Filter Development · Threat Triage

---

### 🐍 [Python Security Automation Labs ⭐](https://github.com/CodeBroKinty/python-automation-labs)
**18 production-ready security automation tools** aligned with CompTIA Security+ domains and enterprise tooling (Tripwire, Nmap, AWS Trusted Advisor, Fail2Ban).

#### 🛡️ AWS Security Suite
- **S3 Security Auditor** — Risk scoring (CRITICAL/HIGH/MEDIUM/LOW) targeting misconfigurations behind the Capital One breach ($190M settlement)
- **IAM Permission Analyzer** — Flags missing MFA, excessive admin access, and unused credentials
- **EC2 Inventory Tool** — Asset discovery with public IP exposure and default security group detection
- **Cost Monitor** — Trend analysis and month-end forecasting to prevent unauthorized spend

#### 🌐 Network Reconnaissance
- **Port Scanner** — 100 concurrent threads, 1,000 ports in 10 seconds (100x speedup vs sequential)
- **Service Detector** — Banner grabbing with OS fingerprinting
- **Ping Sweep** — CIDR notation network discovery and asset mapping
- **Unified Scanner** — Complete host discovery, port scanning, and service enumeration

#### 🚨 Cybersecurity Automation
- **Brute-Force Detector** — 3-layer detection: velocity attacks, distributed coordinated IPs, account enumeration patterns
- **File Integrity Monitor** — Real-time SHA-256 cryptographic hashing to detect unauthorized modifications
- **Authentication Log Parser** — Regex-based threat correlation and attack pattern identification
- **Security Reporter** — Multi-format exports (CSV, Markdown, JSON)

---

### 🏢 [Active Directory IAM Lab](https://github.com/CodeBroKinty/active-directory-iam-lab)
Designed and administered a simulated corporate IAM environment on Windows Server 2025 demonstrating the full identity lifecycle.

- Deployed Windows Server 2025 DC in VirtualBox, created `corp.local` with 4 OUs (IT, HR, Finance, Terminated) and 3 RBAC security groups
- Provisioned 10 users via PowerShell bulk script and executed full **JML lifecycle**: Joiner provisioning, Mover access transfer with old access revoked, Leaver account disabled and moved to Terminated OU
- Ran PowerShell access audit — identified 2 critical findings: **Bob Harris** (IT) in Finance group (High) and **David Kim** (HR) in IT Admins group (Critical)
- Documented findings with severity ratings and remediation recommendations in full lab report

**Skills:** Active Directory · IAM · RBAC · Group Policy · JML Lifecycle · PowerShell · Least Privilege · Access Auditing · Windows Server 2025

---

## 🛠️ Homelab Projects

### [Splunk SIEM Lab](https://github.com/CodeBroKinty/splunk-siem-lab)
Deployed Splunk, ingested endpoint and authentication log data, and performed threat hunting using SPL queries. Identified simulated security incidents including failed login patterns, off-hours authentication, and privilege escalation attempts. Documented findings in incident report format.

**Skills:** Splunk · SIEM · SPL Queries · Log Analysis · Threat Hunting · Incident Documentation

---

### [Wazuh EDR Homelab](https://github.com/CodeBroKinty/wazuh-edr-homelab)
Deployed Wazuh open-source EDR across a multi-OS homelab environment (Parrot OS and Windows). Configured endpoint agents, triggered and analyzed security alerts including failed logins and file integrity changes, and documented findings using industry-standard incident reporting format.

**Skills:** EDR · Wazuh · Endpoint Monitoring · Alert Triage · Incident Reporting · Parrot OS · Linux · Windows Server

---

### Virtualized Attack / Defense Lab
VirtualBox environment running Kali Linux (attacker), Parrot OS, Ubuntu (analyst), and Windows (victim) for penetration testing, log analysis, and defensive security practice.

**Skills:** Kali Linux · Parrot OS · Ubuntu · Windows · VirtualBox · Network Scanning · Threat Analysis

---

## 💻 Tech Stack

**Languages:** Python 3.14+, PowerShell, Bash, SQL (foundational), HTML, CSS

**Cloud:** AWS (EC2, S3, IAM, Cost Explorer), boto3 SDK

**Security Tools:** Splunk, Wazuh, Wireshark, Nessus, MITRE ATT&CK

**IAM & Identity:** Active Directory, LDAPS, RBAC, Group Policy, JML Lifecycle, PowerShell

**Networking:** TCP/IP, DNS, DHCP, SSH, HTTP/HTTPS, Kerberos, NBNS, SAMR, MX Records, Port Scanning, Banner Grabbing, OS Fingerprinting, CIDR Notation

**Operating Systems:** Linux (Ubuntu, Kali, Parrot OS), Windows Server 2025, Windows 10/11

**Concepts:** Threat Detection · Log Analysis · Incident Response · Vulnerability Management · NIST · HIPAA · Cloud Security · File Integrity Monitoring · IAM Auditing · Network Forensics

**Tools:** Git · GitHub · VS Code · VirtualBox · WSL2 · Obsidian · Notion

---

## 📚 Current Training

| Platform | Path | Status |
|---|---|---|
| TryHackMe | Pre-Security Path | ✅ Completed |
| TryHackMe | Cyber Security Path | 🔄 60% Complete |
| AWS | Cloud Practitioner | 🔄 In Progress (July 2026) |

---

## 💼 Professional Background

- **IT & Digital Systems Consultant** — Infrastructure support, Google Workspace administration, and DNS/domain management for healthcare and transport clients in Arkansas and DFW
- **Pharmacy Automation Specialist** — Operated and troubleshot the Omnicell M5000 automated dispensing system alongside Omnicell engineering staff in a high-stakes, zero fault-tolerance environment
- **7 Years Trading Experience** — SPY, IWM, QQQ including 0DTE options strategies with structured risk management

---

## 📈 Current Focus

- ☁️ AWS Cloud Practitioner — In Progress (Target: July 2026)
- 🔬 Expanding homelab with cloud-integrated security monitoring
- 📋 CompTIA SecAI+ (CY0-001) — roadmap target
- ☁️ AWS Security Specialty — roadmap target
- 🏗️ AWS Solutions Architect — roadmap target
- 🤖 AWS Machine Learning Specialty — roadmap target
- 🎯 Open to: **Security Analyst · SOC Analyst · IT Support · Cloud Security Engineer**

---

## 📫 Connect With Me

[![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=flat&logo=twitter&logoColor=white)](https://x.com/CodeBroKinty)
[![Substack](https://img.shields.io/badge/Substack-FF6719?style=flat&logo=substack&logoColor=white)](https://substack.com/@codebrokinty)

📍 DFW Area — Remote & Hybrid Open

---

💡 *Building in public. Documenting the journey from trader to cloud security engineer.*
