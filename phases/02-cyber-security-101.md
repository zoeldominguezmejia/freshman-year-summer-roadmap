# Phase 2 — Cybersecurity Fundamentals Through a DFIR Lens
**Timeline: June 16 – July 10 | ~55 hours | ~17 hrs/week | 🔄 In Progress**

---

## Overview

This phase builds broad technical fluency across offensive and defensive security — but the framing is different from a general cybersecurity curriculum. Every room is approached with one additional question: *what artifacts does this attack or technique generate, and where do they live?*

The goal is not to become an offensive security specialist. The goal is to understand attacks well enough to reconstruct them from evidence. An examiner who understands how Metasploit stages a payload can look at Prefetch data and event logs and reason backwards to the infection. That's the skill this phase builds.

---

## Room Checklist

> **Pace guide:** ⭐ = go slow, take full notes | ➡️ = normal pace | ⚡ = complete it, move on

### Section 1: Start Your Cyber Security Journey
- [x] ⚡ Offensive Security Intro *(overlap from Phase 1)*
- [x] ➡️ Defensive Security Intro
- [x] ➡️ Search Skills

### Section 2: Linux Fundamentals
- [x] ➡️ Linux Fundamentals Part 1
- [x] ➡️ Linux Fundamentals Part 2
- [x] ➡️ Linux Fundamentals Part 3

### Section 3: Windows and AD Fundamentals
- [x] ⭐ Windows Fundamentals 1 — *registry, file system, user accounts: all artifact sources*
- [x] ⭐ Windows Fundamentals 2 — *system tools and configuration; understand what each one logs*
- [x] ⭐ Windows Fundamentals 3 — *security features; understand what generates what evidence*
- [x] ⭐ Active Directory Basics — *enterprise cases almost always involve AD; take notes on users, groups, GPO, domain controllers*

### Section 4: Command Line
- [x] ⭐ Windows Command Line — *you will run these commands during triage and examination*
- [x] ⭐ Windows PowerShell — *PowerShell is both an attacker tool and an artifact source; know both sides*
- [x] ➡️ Linux Shells

### Section 5: Networking
- [x] ➡️ Networking Concepts
- [x] ➡️ Networking Essentials
- [x] ➡️ Networking Core Protocols
- [x] ➡️ Networking Secure Protocols
- [x] ⭐ Wireshark: The Basics — *PCAP analysis is a core examiner skill*
- [x] ➡️ Tcpdump: The Basics
- [x] ⚡ Nmap: The Basics — *attacker tool; understand what it does and what logs it generates*

### Section 6: Cryptography
- [x] ➡️ Cryptography Basics
- [x] ➡️ Public Key Cryptography Basics
- [x] ⭐ Hashing Basics — *MD5 and SHA-256 are how you prove evidence integrity in court*
- [x] ⚡ John the Ripper: The Basics

### Section 7: Exploitation Basics
- [ ] ⚡ Moniker Link (CVE-2024-21413)
- [ ] ⚡ Metasploit: Introduction
- [ ] ⚡ Metasploit: Exploitation
- [ ] ⚡ Metasploit: Meterpreter
- [ ] ➡️ Blue — *Windows exploitation room; the artifacts it generates are things you will later hunt as an examiner*

### Section 8: Web Hacking
- [ ] ➡️ Web Application Basics
- [ ] ⚡ JavaScript Essentials
- [ ] ➡️ SQL Fundamentals — *browser history, communication apps, and many applications store data in SQLite*
- [ ] ⚡ Burp Suite: The Basics

### Section 9: Offensive Security Tooling
- [ ] ⚡ Hydra
- [ ] ⚡ Gobuster: The Basics
- [ ] ⚡ Shells Overview — *understanding shell types helps recognize execution artifacts*
- [ ] ⚡ SQLMap: The Basics

### Section 10: Defensive Security
- [ ] ⚡ Defensive Security Intro
- [ ] ➡️ SOC Fundamentals
- [ ] ⭐ Digital Forensics Fundamentals — *your specialty; go slow, take full notes on every artifact type introduced*
- [ ] ⭐ Incident Response Fundamentals — *learn the IR lifecycle; examiners operate inside this framework*
- [ ] ⭐ Logs Fundamentals — *logs are evidence; know what each log type records, where it lives, and how long it persists*

### Section 11: Security Solutions
- [ ] ➡️ Introduction to SIEM
- [ ] ➡️ Firewall Fundamentals
- [ ] ➡️ IDS Fundamentals
- [ ] ⚡ Vulnerability Scanner Overview

### Section 12: Defensive Security Tooling
- [ ] ⭐ CyberChef: The Basics — *you will use CyberChef constantly: decoding strings, extracting IOCs, identifying file magic bytes*
- [ ] ⭐ CAPA: The Basics — *identifies malware capabilities from binaries without executing them; directly relevant to safe malware triage*
- [ ] ⭐ REMnux: Getting Started — *set this VM up properly; you will use it in projects*
- [ ] ➡️ FlareVM: Arsenal of Tools

### Section 13: Build Your Cyber Security Career
- [ ] ➡️ Security Principles
- [ ] ➡️ Careers in Cyber
- [ ] ⚡ Training Impact on Teams

### Section 14: OWASP Top 10 (2025)
- [ ] ⚡ OWASP Top 10 2025: IAAA Failures
- [ ] ⚡ OWASP Top 10 2025: Application Design Flaws
- [ ] ⚡ OWASP Top 10 2025: Insecure Data Handling

---

## Week-by-Week Schedule

**Week 3 (June 16–22):** Sections 1–4 — Linux Fundamentals, Windows + AD Basics, Command Line, start Networking

**Week 4 (June 23–29):** Finish Section 5 (Wireshark, Tcpdump, Nmap) → Section 6 (Cryptography, extra time on Hashing) → Section 7 (Exploitation suite + Blue)

**Week 5 (June 30–July 6):** Sections 8–9 (Web Hacking, Offensive Tooling) → Section 10 — go slowly through Digital Forensics Fundamentals, IR Fundamentals, Logs Fundamentals

**Week 6 partial (July 7–10):** Sections 11–14 — Defensive Tooling (significant time on CyberChef, CAPA, REMnux), OWASP

---

## Priority Rooms for a Forensic Examiner

**Digital Forensics Fundamentals** — The first structured introduction to the examiner's workflow. Every artifact type introduced here gets its own phase later. Take full notes.

**Incident Response Fundamentals** — Learn the six-phase IR lifecycle: Preparation → Identification → Containment → Eradication → Recovery → Lessons Learned. Forensic examiners are almost always called in during the Identification and Containment phases.

**Logs Fundamentals** — Logs are evidence. Know what each log type records, where it lives on disk, and how long it persists by default. This knowledge is what separates an examiner from a tool operator.

**CAPA: The Basics** — CAPA analyzes binaries without executing them and maps capabilities to MITRE ATT&CK. In a forensic context, this lets you triage suspected malware safely and document its capabilities for your report without risking execution on your analysis machine.

**Active Directory Basics** — Enterprise forensic cases almost always involve an AD environment. Understanding users, groups, OUs, GPO, and domain controllers lets you interpret the artifacts you find on domain-joined machines.

---

## References

- [SWGDE Best Practices](https://www.swgde.org/documents/published)
- [Gary Kessler's File Signatures Table](https://www.garykessler.net/library/file_sigs.html)
- [PortSwigger Web Security Academy](https://portswigger.net/web-security) — companion to Section 8
- [GTFOBins](https://gtfobins.github.io/) — Unix binaries abusable for privilege escalation; useful for understanding attacker behavior you will later reconstruct
- [Varonis Active Directory Overview](https://www.varonis.com/blog/active-directory) — clear, free AD reference

---

*[← Phase 1](./01-pre-security.md) | [Back to Roadmap](../README.md) | [Phase 3 →](./03-soc-level-1.md)*
