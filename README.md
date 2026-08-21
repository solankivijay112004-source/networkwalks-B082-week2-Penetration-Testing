<div align="center">

# 🔐 Cybersecurity Internship – Week 02

### Footprinting & Network Scanning 

![Program](https://img.shields.io/badge/program-Networkwalks%20B082-blue)
![Scope](https://img.shields.io/badge/scope-authorized%20only-important)

A hands-on penetration testing practical combining **passive footprinting** against a live authorized domain and **active network scanning** on a Own System IP Addresse industry-standard Kali Linux and Nmap/Zenmap tooling.

</div>

---

## 📌 Project Overview

| | |
|---|---|
| **Intern** | Vijay Solanki |
| **Program / Batch** | B082 – Networkwalks |
| **Report Date** | 17 August 2026 |
| **Targets** |1. `networkwalks.com` (written permission secured) <br> 2. Own IP Address (`0.0.0.0`) |
| **Phases Covered** | Phase 1: Reconnaissance & Footprinting<br>Phase 2: Scanning & Network Discovery |

> ⚠️ **Authorization Notice:** All activities were performed only against systems I own, have explicit written permission to test, or on my own IP Addresse strictly for educational purposes. No exploitation, intrusion, or unauthorized access was performed at any stage.

---

## 🎯 Objectives

- Identify domain registration details, ownership, and name server configuration
- Fingerprint web technologies, CMS, and software versions in use
- Resolve the target domain to its authoritative IP address
- Inspect HTTP response headers for server and routing information
- Detect the presence of a Web Application Firewall (WAF)
- Enumerate the full DNS record set (NS, MX, TXT, SRV)
- Install and configure Nmap + Zenmap GUI on Windows
- Identify local network addressing via `ipconfig`
- Discover live hosts with a Ping Scan
- Visualize and export network topology
- Run an Intense Scan to identify open ports, services, and versions

---

## 🧰 Tools Used

| Tool | Phase | Purpose |
|---|---|---|
| `whois` | Footprinting | Domain registration lookup |
| `whatweb` | Footprinting | Web technology / CMS / plugin fingerprinting |
| `nslookup` | Footprinting | DNS resolution to IP address |
| `curl -I` | Footprinting | HTTP response header inspection |
| `wafw00f` | Footprinting | Web Application Firewall detection |
| `dnsrecon` | Footprinting | Full DNS record enumeration |
| Kali Linux | Footprinting | OS for reconnaissance tools |
| Nmap (v7.991) | Scanning | Core scanning engine — host/port/service discovery |
| Zenmap (Nmap GUI) | Scanning | Graphical scan configuration, results, topology |
| Npcap 1.88 | Scanning | Packet-capture driver for Windows |
| Windows 11 + `ipconfig` | Scanning | Local network identification |

---

## 🧪 Methodology

### Part A — Footprinting & Reconnaissance (`networkwalks.com`)

Six passive, non-intrusive tasks performed entirely with read-only public queries:

---
1. **Domain Registration Lookup** (`whois`) — registrar, creation/expiry dates, name servers
<img width="1762" height="996" alt="kali1" src="https://github.com/user-attachments/assets/9b2e6f92-4431-41b6-9c0a-ea8cc412bf21" />

---
2. **Web Technology Fingerprinting** (`whatweb`) — CMS, plugins, framework versions

   <img width="1652" height="642" alt="kali2" src="https://github.com/user-attachments/assets/b4fa04ef-03f9-47c6-b995-802d435d84f2" />

---
3. **DNS Resolution** (`nslookup`) — authoritative IP resolution

   !<img width="1652" height="648" alt="kali3" src="https://github.com/user-attachments/assets/b3364e72-3a0c-4279-8263-af6797cd1fee" />

---
4. **HTTP Header Inspection** (`curl -I`) — server banner, cookies, hidden endpoints

   <img width="1642" height="633" alt="kali4" src="https://github.com/user-attachments/assets/43cbb655-f230-4984-ab34-8c67b02cec9c" />

---
5. **WAF Detection** (`wafw00f`) — firewall vendor identification

  <img width="1767" height="922" alt="kali5" src="https://github.com/user-attachments/assets/d0fc19f9-58ad-4f4e-994c-c941cd780997" />

---
6. **DNS Record Enumeration** (`dnsrecon`) — NS, MX, TXT, SRV record mapping

   <img width="1758" height="915" alt="kali6" src="https://github.com/user-attachments/assets/a941e40e-0c95-4527-9dd8-518404668654" />

---
### Part B — Network Scanning with Nmap & Zenmap (Local LAN)

1. Downloaded and installed Nmap 7.991 + Zenmap GUI + Npcap on Windows 11

   <img width="1763" height="968" alt="nm1" src="https://github.com/user-attachments/assets/3c99cfe8-26df-4bfe-a90a-51f3ecc4354a" />

---
2. Identified local IP, subnet mask, and gateway via `ipconfig`

   <img width="1470" height="743" alt="nm7" src="https://github.com/user-attachments/assets/f7083408-7ac4-4a83-8b91-247ab0f65fd6" />

---
3. Ran a **Ping Scan** (`nmap -sn Own IP Addresse) to discover live hosts

   <img width="1896" height="1013" alt="nm8" src="https://github.com/user-attachments/assets/6122ff7c-444a-495a-9521-7d3abac2a62f" />

---
4. Visualized and exported network topology (PDF)

  <img width="1892" height="1012" alt="nm10" src="https://github.com/user-attachments/assets/511f08c1-af3a-45ac-a705-71a058ff26b6" />

---
5. Ran an **Intense Scan** (`nmap -T4 -A -v Own IP Addresse`) for OS/service/version detection

   <img width="1897" height="1010" alt="nm12" src="https://github.com/user-attachments/assets/5aa820e3-8fc1-4c2e-8d68-763b11e9fbdb" />

---
6. Reviewed open ports and running services

   <img width="1893" height="1012" alt="nm13" src="https://github.com/user-attachments/assets/9392caae-f065-46f7-90a7-e6928d47be39" />


---

## 🔍 Key Findings

### Footprinting — Consolidated Profile

| Attribute | Value |
|---|---|
| Registrar | GoDaddy.com, LLC |
| Hosting Provider | HostGator |
| Resolved IP | `Own IP Addresse` |
| Web Server | Apache |
| CMS / Version | WordPress 7.0.4 |
| Notable Plugin | WordPress Download Manager 3.3.58 |
| WAF | ModSecurity (SpiderLabs) — Detected |
| Mail Server | mail.networkwalks.com |

### Network Scanning — Open Ports (Local Host)

| Port | Protocol | Service | Description |
|---|---|---|---|
| 135 | TCP | msrpc | Microsoft Windows RPC endpoint mapper |
| 139 | TCP | netbios-ssn | Microsoft Windows NetBIOS Session Service |
| 445 | TCP | microsoft-ds | SMB file/printer sharing service |

These are commonly exposed by default on Windows systems for file/printer sharing but are frequently targeted in SMB-based exploits and lateral movement.

---

## ⚠️ Risk Analysis Summary

| Finding | Risk Level |
|---|---|
| Domain ownership/registrar details exposed | Low |
| CMS & plugin versions fingerprintable | Medium |
| Hosting IP resolvable | Medium |
| HTTP headers disclose stack & endpoints | Low |
| WAF vendor identifiable | Informational |
| Full DNS/mail footprint enumerable | Medium |
| RPC endpoint mapper (135) exposed | Medium |
| NetBIOS session service (139) exposed | Medium |
| SMB service (445) exposed | **High** |
| Full host/service map obtainable | Medium |

> These are discovery-stage observations, not confirmed vulnerabilities. No exploitation or vulnerability validation was performed.

---

## ✅ Recommendations (Selected)

- Patch/update WordPress core and the WordPress Download Manager plugin
- Minimize HTTP header/version disclosure; restrict public `/wp-json/` exposure
- Enable WHOIS domain privacy protection
- Continue tuning the ModSecurity (SpiderLabs) WAF rule set
- Periodically audit SPF/MX/SRV DNS records
- Disable SMB (445), NetBIOS (139), and RPC (135) on hosts that don't need them
- Restrict SMB access to trusted internal management systems only
- Apply the latest Windows security updates, especially SMB-related patches
- Segment networks to isolate general-purpose/IoT devices from sensitive systems
- Conduct recurring self-reconnaissance to catch new public exposure early

*(Full list of 12 recommendations available in the complete report.)*

---

## 📁 Repository Structure

```
├── report/
│   └── W2-PM-FINAL_Report.pdf     # Full report with methodology & evidence log
├── evidence/
│   ├── part-a/                    # Footprinting screenshots (whois, whatweb, nslookup, curl, wafw00f, dnsrecon)
│   └── part-b/                    # Scanning screenshots (install, ipconfig, ping scan, topology, intense scan, ports)
└── README.md
```

---

## 🧠 Key Takeaway

Passive reconnaissance and active network scanning are complementary discovery techniques that form the foundation of every real-world security assessment. Reducing unnecessary public exposure of software versions and infrastructure details — combined with disabling unneeded local services — directly shrinks an organization's attack surface.

---

## ⚖️ Disclaimer

This material is for education and authorized research purposes only. Unauthorized access to computer systems is illegal in most jurisdictions, even when no damage occurs. All activities documented here were performed only against systems I own, have explicit written permission to test, or on my own IP Addresse.

---

👤 Author
--------------------------------------------
###  Vijay Solanki
**Cybersecurity Intern B082**  

LinkedIn: https://www.linkedin.com/in/solanki-vijay/
