# Cybersecurity Fundamentals Through a DFIR Lens

**Timeline: June 16 – July 10 | ~55 hours | ~17 hrs/week**
---

## 🎯 Goal
Build broad technical fluency across offensive and defensive cybersecurity while beginning to develop the forensic examiner's lens: what artifacts does each attack leave behind? This is TryHackMe's flagship 101 path — 14 sections covering Linux, Windows, networking, cryptography, web hacking, and defensive tooling. For you, the priority rooms are the ones that directly answer the question: *what evidence does this generate, and where does it live?*

---
## Professional Development Objective

The purpose of this phase is not to become an offensive security specialist.

Instead, the objective is to understand:

- How attacks occur
- What evidence attacks leave behind
- Where forensic artifacts are stored
- How defenders detect malicious activity

---

## ✅ Full Room Checklist

> **Key:** ⭐ = go slow, take full notes | ➡️ = normal pace | ⚡ = go fast, just complete it

### Section 1: Start Your Cyber Security Journey
- [x] ⚡ Offensive Security Intro *(overlap from Phase 1 — just complete it)*
- [x] ➡️ Defensive Security Intro *(overlap from Phase 1 — quick but read carefully)*
- [x] ➡️ Search Skills

### Section 2: Linux Fundamentals
- [x] ➡️ Linux Fundamentals Part 1
- [x] ➡️ Linux Fundamentals Part 2
- [x] ➡️ Linux Fundamentals Part 3
> Linux matters for forensics — you will examine Linux file systems and parse Linux logs.
> Normal pace is fine; you don't need to master scripting yet, just get comfortable in the CLI.

### Section 3: Windows and AD Fundamentals
- [x] ⭐ Windows Fundamentals 1 *(registry, file system, user accounts — all artifact sources)*
- [x] ⭐ Windows Fundamentals 2 *(system tools and configuration — understand what each one logs)*
- [x] ⭐ Windows Fundamentals 3 *(security features — understand what generates what evidence)*
- [x] ⭐ Active Directory Basics *(enterprise cases almost always involve AD — take notes on users, groups, GPO, domain controllers)*

### Section 4: Command Line
- [x] ⭐ Windows Command Line *(you will run these commands during triage and examination)*
- [ ] ⭐ Windows PowerShell *(PowerShell is both an attacker tool and an artifact source — know both sides)*
- [ ] ➡️ Linux Shells

### Section 5: Networking
- [ ] ➡️ Networking Concepts
- [ ] ➡️ Networking Essentials
- [ ] ➡️ Networking Core Protocols
- [ ] ➡️ Networking Secure Protocols
- [ ] ⭐ Wireshark: The Basics *(PCAP analysis is a core examiner skill — go slow)*
- [ ] ➡️ Tcpdump: The Basics
- [ ] ⚡ Nmap: The Basics *(attacker tool — just understand what it does and what logs it generates)*

### Section 6: Cryptography
- [ ] ➡️ Cryptography Basics
- [ ] ➡️ Public Key Cryptography Basics
- [ ] ⭐ Hashing Basics *(MD5 and SHA-256 are how you prove evidence integrity in court — internalize this)*
- [ ] ⚡ John the Ripper: The Basics *(password cracking tool — just complete it, minimal forensics relevance)*

### Section 7: Exploitation Basics
- [ ] ⚡ Moniker Link (CVE-2024-21413) *(just complete it)*
- [ ] ⚡ Metasploit: Introduction *(just complete it)*
- [ ] ⚡ Metasploit: Exploitation *(just complete it)*
- [ ] ⚡ Metasploit: Meterpreter *(just complete it)*
- [ ] ➡️ Blue *(this one is worth a normal pass — it's a Windows exploitation room and the artifacts it generates are things you'll later hunt as an examiner)*

### Section 8: Web Hacking
- [ ] ➡️ Web Application Basics
- [ ] ⚡ JavaScript Essentials *(just complete it)*
- [ ] ➡️ SQL Fundamentals *(databases appear in forensic cases — browser history, communication apps, and many applications store data in SQLite)*
- [ ] ⚡ Burp Suite: The Basics *(pentester tool — just complete it)*

### Section 9: Offensive Security Tooling
- [ ] ⚡ Hydra *(just complete it)*
- [ ] ⚡ Gobuster: The Basics *(just complete it)*
- [ ] ⚡ Shells Overview *(skim it — understanding shell types helps you recognize execution artifacts)*
- [ ] ⚡ SQLMap: The Basics *(just complete it)*

### Section 10: Defensive Security
- [ ] ⚡ Defensive Security Intro *(you've seen this — just complete it)*
- [ ] ➡️ SOC Fundamentals
- [ ] ⭐ Digital Forensics Fundamentals *(your specialty — go slow, take full notes on every artifact type introduced)*
- [ ] ⭐ Incident Response Fundamentals *(learn the IR lifecycle cold — examiners operate inside this framework)*
- [ ] ⭐ Logs Fundamentals *(logs are evidence — know what each log type records, where it lives, and how long it persists)*

### Section 11: Security Solutions
- [ ] ➡️ Introduction to SIEM
- [ ] ➡️ Firewall Fundamentals
- [ ] ➡️ IDS Fundamentals
- [ ] ⚡ Vulnerability Scanner Overview *(just complete it)*

### Section 12: Defensive Security Tooling
- [ ] ⭐ CyberChef: The Basics *(you will use CyberChef constantly — decoding strings, extracting IOCs, identifying file magic bytes)*
- [ ] ⭐ CAPA: The Basics *(identifies malware capabilities from binaries without executing them — directly relevant to safe malware triage in casework)*
- [ ] ⭐ REMnux: Getting Started *(set this VM up properly and get comfortable in it — you will use it in projects)*
- [ ] ➡️ FlareVM: Arsenal of Tools *(worth a normal pass — know what tools are available and what each does)*

### Section 13: Build Your Cyber Security Career
- [ ] ➡️ Security Principles
- [ ] ➡️ Careers in Cyber
- [ ] ⚡ Training Impact on Teams *(just complete it)*

### Section 14: OWASP Top 10 (2025)
- [ ] ⚡ OWASP Top 10 2025: IAAA Failures *(just complete it)*
- [ ] ⚡ OWASP Top 10 2025: Application Design Flaws *(just complete it)*
- [ ] ⚡ OWASP Top 10 2025: Insecure Data Handling *(just complete it — SQL injection and improper data handling do show up in forensic cases involving web logs)*
---

## 📝 Phase 2 Schedule

### Week 3 (June 16 – June 22) — OS, CLI, and Networking
- TryHackMe: Sections 1–4 (Linux Fundamentals, Windows + AD Basics, Command Line)
- TryHackMe: Begin Section 5 (Networking Concepts through Networking Secure Protocols)

### Week 4 (June 23 – June 29) — Networking Tools, Crypto, and Exploitation
- TryHackMe: Finish Section 5 (Wireshark, Tcpdump, Nmap)
- TryHackMe: Section 6 (Cryptography — spend extra time on Hashing Basics)
- TryHackMe: Section 7 (Exploitation — Metasploit suite and Blue)

### Week 5 (June 30 – July 6) — Web Hacking and Forensics Fundamentals Deep Pass
- TryHackMe: Sections 8–9 (Web Hacking, Offensive Tooling)
- TryHackMe: Section 10 — go slowly through Digital Forensics Fundamentals, IR Fundamentals, and Logs Fundamentals

### Week 6 partial (July 7 – July 10) — Defensive Tooling and OWASP
- TryHackMe: Sections 11–14
- Spend significant time on CyberChef, CAPA, and REMnux
---

## ⭐ Priority Rooms for a Forensic Examiner

**Hashing Basics** — Hash verification is how you prove in court that the evidence file you examined is byte-for-byte identical to the original. MD5 and SHA-256 are the first thing you calculate when you receive evidence. Get comfortable with why collision resistance matters.

**Digital Forensics Fundamentals** — The first structured introduction to the examiner's workflow. Take full notes. Every artifact type introduced here gets an entire phase later.

**Incident Response Fundamentals** — Learn the six-phase IR lifecycle: Preparation → Identification → Containment → Eradication → Recovery → Lessons Learned. Forensic examiners are almost always called in during the Identification and Containment phases.

**Logs Fundamentals** — Logs are evidence. Windows Event Logs, Syslog, application logs — understand what each records, where it lives on disk, and how long it persists by default.

**CAPA: The Basics** — CAPA analyzes binaries without executing them and maps capabilities to MITRE ATT&CK. In a forensic context, this lets you triage suspected malware safely and document its capabilities for your report.

**Active Directory Basics** — Enterprise forensic cases almost always involve an AD environment. Understanding users, groups, OUs, GPO, and domain controllers lets you interpret the artifacts you will find on domain-joined machines.

---

## 🔗 Supplemental Resources

- **SWGDE Best Practices:** [swgde.org](https://www.swgde.org/documents/published) — Professional standards documents for digital forensic examiners. Begin reading.
- **Gary Kessler's File Signatures Table:** [garykessler.net](https://www.garykessler.net/library/file_sigs.html) — Indispensable for file carving and identifying file types from raw hex.
- **PortSwigger Web Security Academy:** [portswigger.net/web-security](https://portswigger.net/web-security) — Companion to Section 8 web hacking rooms.
- **GTFOBins:** [gtfobins.github.io](https://gtfobins.github.io/) — Unix binaries abusable for privilege escalation; useful to understand attacker behavior you will later reconstruct.
- **AD Visual Reference:** [Varonis Active Directory Overview](https://www.varonis.com/blog/active-directory) — Clear, free AD reference.

---

*[← Phase 1](./01-pre-security.md) | [Back to Main Roadmap](../README.md) | [Phase 3 →](./03-soc-level-1.md)*
