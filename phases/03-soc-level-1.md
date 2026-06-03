# Phase 3 — SOC Level 1 & Enterprise SIEM Integration
**Timeline: July 10 – July 28 | ~50 hours | ~17 hrs/week**

---

## 🎯 Goal
Learn to operate as a Security Operations Center Level 1 analyst. This phase ties hands-on log hunting, SIEM triage, phishing analysis, and network monitoring with the enterprise detection frameworks in the Google Cybersecurity Certificate.

---

## 📚 Dual-Platform Alignment

### 1. TryHackMe: SOC Level 1 Path
14 sections covering the full SOC analyst workflow — from alert triage to malware classification to capstone investigations.

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
- [ ] Pyramid Of Pain ⭐ *(memorize this — it comes up in interviews)*
- [ ] Cyber Kill Chain ⭐
- [ ] Unified Kill Chain
- [ ] MITRE ⭐ *(most important framework in defensive security)*
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
- [ ] Wireshark: The Basics *(quick pass — covered in Phase 2)*
- [ ] Wireshark: Packet Operations ⭐
- [ ] Wireshark: Traffic Analysis ⭐
- [ ] NetworkMiner

### Section 7: Network Security Monitoring
- [ ] Network Security Essentials
- [ ] Network Discovery Detection
- [ ] Data Exfiltration Detection ⭐ *(directly relevant to insider threat forensics)*
- [ ] Man-in-the-Middle Detection
- [ ] IDS Fundamentals *(quick pass — covered in Phase 2)*
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
- [ ] Living Off the Land Attacks ⭐ *(LOLBins — every DFIR interview asks about this)*
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

### Week 7 (July 10 – July 16) — Focus: SOC Fundamentals, Frameworks, and Phishing
- TryHackMe: Sections 1–2 (Blue Team Intro, SOC Team Internals)
- TryHackMe: Section 3 (Core SOC Solutions — Splunk, Elastic, EDR, SOAR)
- TryHackMe: Section 4 (Cyber Defence Frameworks — Pyramid of Pain, Kill Chain, MITRE)
- TryHackMe: Section 5 (Phishing Analysis — all 7 rooms)
- Coursera: Begin Google Module 5 (Assets, Threats, and Vulnerabilities)

### Week 8 (July 17 – July 23) — Focus: Traffic Analysis, Windows/Linux Monitoring, Malware
- TryHackMe: Section 6 (Network Traffic Analysis — Wireshark deep pass, NetworkMiner)
- TryHackMe: Section 7 (Network Security Monitoring — Snort, Data Exfiltration Detection)
- TryHackMe: Sections 8–10 (Web, Windows, and Linux Security Monitoring)
- TryHackMe: Section 11 (Malware Concepts — classification, LOLBins, intro analysis)
- Coursera: Complete Google Module 5, begin Module 6

### Week 9 partial (July 24 – July 28) — Focus: Threat Intel, SIEM Triage, Capstones
- TryHackMe: Section 12 (Threat Analysis Tools)
- TryHackMe: Section 13 (SIEM Triage — Splunk and Elastic alert triage labs)
- TryHackMe: Section 14 (Capstone Challenges — Tempest, Boogeyman 1–3)
- Coursera: Complete Module 6, begin Module 7 (Python automation)
- **Milestone:** Earn **SAL1 SOC Analyst Level 1 Certificate** from TryHackMe

---

## ⭐ Priority Rooms to Slow Down On

**MITRE** — Map every attack you see to a tactic and technique throughout this entire phase. Use attack.mitre.org constantly. Interviewers will ask you to do this on the spot.

**Pyramid of Pain** — Understand why blocking IOCs at different levels has different impact on an attacker. This framework comes up in both interviews and real SOC work constantly.

**Windows Threat Detection 1–3** — This is the bridge between SOC work and DFIR. Windows event IDs, Sysmon logs, and artifact correlation are the same skills used in forensic investigations.

**Living Off the Land Attacks** — LOLBins (legitimate system binaries used maliciously) are one of the most common attack techniques in modern incidents. Know certutil, mshta, regsvr32, wmic, and powershell usage patterns cold.

**Boogeyman 1–3** — Treat these as real investigations, not CTF challenges. Write a full IR report for at least one of them using the forensic report schema from Phase 5.

---

## 🔗 Supplemental Resources

- **Boss of the SOC (BOTS) Datasets:** [GitHub](https://github.com/splunk/botsdatasets) — Splunk's official CTF dataset. Practice tracking enterprise-scale attacks with real log data.
- **Any.Run Interactive Sandbox:** [app.any.run](https://app.any.run/) — Watch live malware execute in real-time and view the generated network and process logs.
- **Wireshark Sample Captures:** [Wireshark Wiki](https://wiki.wireshark.org/SampleCaptures) — Repository of real pcap files from malware infections, scans, and protocols.
- **Sigma Rules:** [GitHub](https://github.com/SigmaHQ/sigma) — Write a detection rule once, convert it to Splunk or Elastic queries. Great for understanding how detection logic works.
- **MITRE ATT&CK Navigator:** [mitre-attack.github.io](https://mitre-attack.github.io/attack-navigator/) — Interactive heatmap. Use this to track every technique you encounter across this phase.

---

*[← Phase 2](./02-cyber-security-101.md) | [Back to Main Roadmap](../README.md) | [Phase 4 →](./04-dfir-deep-dive.md)*
