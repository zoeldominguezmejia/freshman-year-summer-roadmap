# Phase 2 — Cyber Security 101 & Forensic Foundations Track
**Timeline: June 15 – July 9 | ~55 hours | ~17 hrs/week**

---

## 🎯 Goal
Build broad technical fluency across offensive and defensive cybersecurity while beginning to develop the forensic examiner's lens: what artifacts does each attack leave behind? This is TryHackMe's flagship 101 path — 14 sections covering Linux, Windows, networking, cryptography, web hacking, and defensive tooling. For you, the priority rooms are the ones that directly answer the question: *what evidence does this generate, and where does it live?*

---

## 📚 Dual-Platform Alignment

### 1. TryHackMe: Cyber Security 101 Path
Hands-on experience across offense and defense. You are not training to be a pentester — you are training to understand what attackers do so you can reconstruct it from artifacts later.

### 2. UNCC Coursera: Google Cybersecurity Certificate (Modules 3 & 4)
Asset classification, network security models, Linux fundamentals for security, and SQL — all of which intersect with forensic examiner work.

---

## ✅ Full Room Checklist

### Section 1: Start Your Cyber Security Journey
- [ ] Offensive Security Intro *(overlap from Phase 1 — quick review)*
- [ ] Defensive Security Intro *(overlap from Phase 1 — quick review)*
- [ ] Search Skills

### Section 2: Linux Fundamentals
- [ ] Linux Fundamentals Part 1
- [ ] Linux Fundamentals Part 2
- [ ] Linux Fundamentals Part 3

### Section 3: Windows and AD Fundamentals
- [ ] Windows Fundamentals 1
- [ ] Windows Fundamentals 2
- [ ] Windows Fundamentals 3
- [ ] Active Directory Basics ⭐ *(critical — AD environments generate the artifacts you will examine in enterprise cases)*

### Section 4: Command Line
- [ ] Windows Command Line
- [ ] Windows PowerShell
- [ ] Linux Shells

### Section 5: Networking
- [ ] Networking Concepts
- [ ] Networking Essentials
- [ ] Networking Core Protocols
- [ ] Networking Secure Protocols
- [ ] Wireshark: The Basics
- [ ] Tcpdump: The Basics
- [ ] Nmap: The Basics

### Section 6: Cryptography
- [ ] Cryptography Basics
- [ ] Public Key Cryptography Basics
- [ ] Hashing Basics ⭐ *(hash verification is the backbone of evidence integrity — do not rush this)*
- [ ] John the Ripper: The Basics

### Section 7: Exploitation Basics
- [ ] Moniker Link (CVE-2024-21413)
- [ ] Metasploit: Introduction
- [ ] Metasploit: Exploitation
- [ ] Metasploit: Meterpreter
- [ ] Blue

### Section 8: Web Hacking
- [ ] Web Application Basics
- [ ] JavaScript Essentials
- [ ] SQL Fundamentals
- [ ] Burp Suite: The Basics

### Section 9: Offensive Security Tooling
- [ ] Hydra
- [ ] Gobuster: The Basics
- [ ] Shells Overview
- [ ] SQLMap: The Basics

### Section 10: Defensive Security
- [ ] Defensive Security Intro *(quick pass)*
- [ ] SOC Fundamentals
- [ ] Digital Forensics Fundamentals ⭐ *(your specialty — go slow and take full notes)*
- [ ] Incident Response Fundamentals ⭐ *(learn the IR lifecycle cold — it is the framework examiners operate inside)*
- [ ] Logs Fundamentals ⭐ *(logs are evidence — understand what each log type records and where it lives)*

### Section 11: Security Solutions
- [ ] Introduction to SIEM
- [ ] Firewall Fundamentals
- [ ] IDS Fundamentals
- [ ] Vulnerability Scanner Overview

### Section 12: Defensive Security Tooling
- [ ] CyberChef: The Basics ⭐ *(you will use CyberChef constantly — decoding, encoding, IOC extraction)*
- [ ] CAPA: The Basics ⭐ *(identifies malware capabilities from binaries without executing them — critical for safe malware triage)*
- [ ] REMnux: Getting Started ⭐ *(your malware analysis VM — set it up properly)*
- [ ] FlareVM: Arsenal of Tools

### Section 13: Build Your Cyber Security Career
- [ ] Security Principles
- [ ] Careers in Cyber
- [ ] Training Impact on Teams

### Section 14: OWASP Top 10 (2025)
- [ ] OWASP Top 10 2025: IAAA Failures
- [ ] OWASP Top 10 2025: Application Design Flaws
- [ ] OWASP Top 10 2025: Insecure Data Handling

### UNCC Coursera — Google Cybersecurity Certificate
- [ ] Module 3: Connect and Protect: Networks and Network Security
- [ ] Module 4: Tools of the Trade: Linux and SQL

---

## 📝 Phase 2 Schedule

### Week 3 (June 15 – June 21) — OS, CLI, and Networking
- TryHackMe: Sections 1–4 (Linux Fundamentals, Windows + AD Basics, Command Line)
- TryHackMe: Begin Section 5 (Networking Concepts through Networking Secure Protocols)
- Coursera: Begin Google Module 3

### Week 4 (June 22 – June 28) — Networking Tools, Crypto, and Exploitation
- TryHackMe: Finish Section 5 (Wireshark, Tcpdump, Nmap)
- TryHackMe: Section 6 (Cryptography — spend extra time on Hashing Basics)
- TryHackMe: Section 7 (Exploitation — Metasploit suite and Blue)
- Coursera: Complete Google Module 3, begin Module 4

### Week 5 (June 29 – July 5) — Web Hacking and Forensics Fundamentals Deep Pass
- TryHackMe: Sections 8–9 (Web Hacking, Offensive Tooling)
- TryHackMe: Section 10 — go slowly through Digital Forensics Fundamentals, IR Fundamentals, and Logs Fundamentals. These three rooms are the first structured exposure to your actual career workflow.
- Coursera: Complete Google Module 4

### Week 6 partial (July 6 – July 9) — Defensive Tooling and OWASP
- TryHackMe: Sections 11–14
- Spend significant time on CyberChef, CAPA, and REMnux
- **Milestone:** Claim **SEC1 Cyber Security 101 Certificate** from TryHackMe

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
