# Phase 3 — SOC Level 1 & Evidence Triage Track
**Timeline: July 11 – July 29 | ~50 hours | ~17 hrs/week**
---

## 🎯 Goal
Learn to operate as a Security Operations Center Level 1 analyst — and more importantly for your path, understand how SOC workflows, log analysis, and alert triage feed evidence into a forensic investigation. Digital forensics examiners often receive cases that were first flagged by a SOC team. Understanding both sides of that handoff makes you a significantly stronger examiner.

---

## 📚 Dual-Platform Alignment

### 1. TryHackMe: SOC Level 1 Path
14 sections covering the full SOC workflow — alert triage, phishing analysis, network monitoring, malware classification, and capstone investigations.

### 2. UNCC Coursera: Google Cybersecurity Certificate (Modules 5–7)
Assets and threat management, detection and response pipelines, and Python automation for security tasks.

---

## ✅ Full Room Checklist

### Section 1: Blue Team Introduction
- [ ] Junior Security Analyst Intro
- [ ] SOC Role in Blue Team
- [ ] Humans as Attack Vectors
- [ ] Systems as Attack Vectors

### Section 2: SOC Team Internals
- [ ] SOC L1 Alert Triage
- [ ] SOC L1 Alert Reporting
- [ ] SOC Workbooks and Lookups
- [ ] SOC Metrics and Objectives
- [ ] Introduction to Phishing

### Section 3: Core SOC Solutions
- [ ] Introduction to EDR
- [ ] Introduction to SIEM
- [ ] Splunk: The Basics ⭐
- [ ] Elastic Stack: The Basics ⭐
- [ ] Introduction to SOAR

### Section 4: Cyber Defence Frameworks
- [ ] Pyramid Of Pain ⭐
- [ ] Cyber Kill Chain ⭐ *(the attacker's timeline that you will later reconstruct from artifacts)*
- [ ] Unified Kill Chain
- [ ] MITRE ⭐ *(most important framework in the field — map every technique you see to ATT&CK)*
- [ ] Summit
- [ ] Eviction

### Section 5: Phishing Analysis
- [ ] Phishing Analysis Fundamentals
- [ ] Phishing Emails in Action
- [ ] Phishing Analysis Tools
- [ ] Phishing Prevention
- [ ] The Greenholt Phish
- [ ] Snapped Phish-ing Line
- [ ] Phishing Unfolding

### Section 6: Network Traffic Analysis
- [ ] Network Traffic Basics
- [ ] Wireshark: The Basics *(quick pass)*
- [ ] Wireshark: Packet Operations ⭐
- [ ] Wireshark: Traffic Analysis ⭐
- [ ] NetworkMiner ⭐ *(excellent for extracting files, credentials, and artifacts from PCAP files)*

### Section 7: Network Security Monitoring
- [ ] Network Security Essentials
- [ ] Network Discovery Detection
- [ ] Data Exfiltration Detection ⭐ *(exfiltration cases are a core examiner scenario — study this closely)*
- [ ] Man-in-the-Middle Detection
- [ ] IDS Fundamentals *(quick pass)*
- [ ] Snort

### Section 8: Web Security Monitoring
- [ ] Web Security Essentials
- [ ] Detecting Web Attacks
- [ ] Detecting Web Shells
- [ ] Detecting Web DDoS

### Section 9: Windows Security Monitoring
- [ ] Windows Logging for SOC ⭐
- [ ] Windows Threat Detection 1 ⭐
- [ ] Windows Threat Detection 2 ⭐
- [ ] Windows Threat Detection 3 ⭐

### Section 10: Linux Security Monitoring
- [ ] Linux Logging for SOC
- [ ] Linux Threat Detection 1
- [ ] Linux Threat Detection 2
- [ ] Linux Threat Detection 3

### Section 11: Malware Concepts for SOC
- [ ] Malware Classification ⭐
- [ ] Intro to Malware Analysis ⭐
- [ ] Living Off the Land Attacks ⭐ *(LOLBins appear in almost every modern incident you will examine)*
- [ ] Shadow Trace

### Section 12: Threat Analysis Tools
- [ ] Intro to Cyber Threat Intel
- [ ] File and Hash Threat Intel
- [ ] IP and Domain Threat Intel
- [ ] Invite Only

### Section 13: SIEM Triage for SOC
- [ ] Log Analysis with SIEM
- [ ] Alert Triage With Splunk ⭐
- [ ] Alert Triage With Elastic ⭐
- [ ] ItsyBitsy
- [ ] Benign

### Section 14: SOC Level 1 Capstone Challenges
- [ ] Tempest
- [ ] Boogeyman 1 ⭐
- [ ] Boogeyman 2 ⭐
- [ ] Boogeyman 3 ⭐

### UNCC Coursera — Google Cybersecurity Certificate
- [ ] Module 5: Assets, Threats, and Vulnerabilities
- [ ] Module 6: Sound the Alarm: Detection and Response
- [ ] Module 7: Automate Cybersecurity Tasks with Python

---

## 📝 Phase 3 Schedule

### Week 7 (July 11 – July 17) — SOC Fundamentals, Frameworks, Phishing
- TryHackMe: Sections 1–2 (Blue Team Intro, SOC Team Internals)
- TryHackMe: Section 3 (Core SOC Solutions — Splunk, Elastic, EDR, SOAR)
- TryHackMe: Section 4 (Cyber Defence Frameworks — Pyramid of Pain, Kill Chain, MITRE)
- TryHackMe: Section 5 (Phishing Analysis — all 7 rooms)
- Coursera: Begin Google Module 5

### Week 8 (July 18 – July 24) — Traffic Analysis, Windows/Linux Monitoring, Malware
- TryHackMe: Section 6 (Network Traffic Analysis — Wireshark deep pass, NetworkMiner)
- TryHackMe: Section 7 (Network Security Monitoring — Snort, Data Exfiltration Detection)
- TryHackMe: Sections 8–10 (Web, Windows, and Linux Security Monitoring)
- TryHackMe: Section 11 (Malware Concepts — classification, LOLBins, intro analysis)
- Coursera: Complete Google Module 5, begin Module 6

### Week 9 partial (July 25 – July 29) — Threat Intel, SIEM Triage, Capstones
- TryHackMe: Section 12 (Threat Analysis Tools)
- TryHackMe: Section 13 (SIEM Triage — Splunk and Elastic)
- TryHackMe: Section 14 (Capstone Challenges — Tempest, Boogeyman 1–3)
- Coursera: Complete Module 6, begin Module 7
- **Milestone:** Earn **SAL1 SOC Analyst Level 1 Certificate** from TryHackMe

---

## ⭐ Priority Rooms for a Forensic Examiner

**Windows Threat Detection 1–3** — Windows Event IDs and Sysmon logs are some of the most valuable artifacts in any forensic investigation. The same skills you develop here for SOC alerting apply directly to forensic timeline reconstruction. Know Event IDs 4624, 4625, 4648, 4688, 4697, 4720, 7045 cold.

**NetworkMiner** — Where Wireshark shows you packets, NetworkMiner extracts artifacts: files transferred, credentials transmitted, host details. This is the network forensics workflow, not just traffic monitoring.

**Data Exfiltration Detection** — Exfiltration is one of the most common forensic case types in corporate environments. Study the detection patterns and then flip the question: if you were the examiner on the receiving end of this case, what artifacts would prove it happened?

**Boogeyman 1–3** — Treat these as forensic investigations, not CTF challenges. For at least one of them, write a full investigation report using the forensic report schema from Phase 5. By doing this now, your Phase 5 projects will be dramatically cleaner.

**MITRE ATT&CK** — Map every technique you encounter throughout this phase to a tactic and technique on attack.mitre.org. By the end of Phase 3 you should be doing this automatically. It will be the first thing interviewers ask you to do.

---

## 🔗 Supplemental Resources

- **MITRE ATT&CK Navigator:** [mitre-attack.github.io/attack-navigator](https://mitre-attack.github.io/attack-navigator/) — Interactive heatmap. Track every technique you see.
- **Boss of the SOC (BOTS) Datasets:** [GitHub](https://github.com/splunk/botsdatasets) — Splunk CTF dataset; practice at enterprise scale.
- **Any.run Interactive Sandbox:** [app.any.run](https://app.any.run/) — Watch malware execute live and capture process and network artifacts.
- **Wireshark Sample Captures:** [Wireshark Wiki](https://wiki.wireshark.org/SampleCaptures) — Real pcap files from infections, scans, and protocols.
- **Windows Event Log Encyclopedia:** [ultimatewindowssecurity.com](https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/) — Definitive reference for every Windows Event ID.

---

*[← Phase 2](./02-cyber-security-101.md) | [Back to Main Roadmap](../README.md) | [Phase 4 →](./04-dfir-deep-dive.md)*
