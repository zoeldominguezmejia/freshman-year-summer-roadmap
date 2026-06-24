# Phase 3 — SOC Level 1 & Evidence Triage
**Timeline: July 11 – July 29 | ~50 hours | ~17 hrs/week**

---

## Overview

This phase teaches SOC Level 1 operations — but the reason it's in a forensics examiner roadmap is deliberate. Digital forensics examiners frequently receive cases that were first flagged by a SOC team. Understanding both sides of that handoff — how analysts detect, triage, and escalate — makes you a significantly stronger examiner.

The two skills that transfer most directly from SOC work to forensics: log analysis and MITRE ATT&CK mapping. Every case you examine will involve parsing logs and mapping behavior to techniques. Build those habits here.

---

## Room Checklist

> **Pace guide:** ⭐ = go slow, take full notes | ➡️ = normal pace | ⚡ = complete it, move on

### Section 1: Blue Team Introduction
- [ ] ➡️ Junior Security Analyst Intro
- [ ] ➡️ SOC Role in Blue Team
- [ ] ⭐ Humans as Attack Vectors — *social engineering is the initial access vector in a large percentage of cases you will examine*
- [ ] ➡️ Systems as Attack Vectors

### Section 2: SOC Team Internals
- [ ] ⭐ SOC L1 Alert Triage — *understand how a case gets handed to an examiner; this is the workflow upstream of your job*
- [ ] ⭐ SOC L1 Alert Reporting — *report writing discipline starts here; the habits are the same ones you need for forensic reports*
- [ ] ➡️ SOC Workbooks and Lookups
- [ ] ⚡ SOC Metrics and Objectives
- [ ] ⭐ Introduction to Phishing — *phishing is the initial access vector you will most commonly reconstruct as an examiner*

### Section 3: Core SOC Solutions
- [ ] ➡️ Introduction to EDR
- [ ] ➡️ Introduction to SIEM
- [ ] ⭐ Splunk: The Basics — *SPL query fluency is a real examiner skill in enterprise environments*
- [ ] ⭐ Elastic Stack: The Basics — *same as Splunk; both platforms appear in enterprise forensic environments*
- [ ] ⚡ Introduction to SOAR

### Section 4: Cyber Defence Frameworks
- [ ] ⭐ Pyramid Of Pain — *memorize this; it frames how you prioritize IOCs in any investigation*
- [ ] ⭐ Cyber Kill Chain — *this is the attacker timeline you will reconstruct from artifacts; know every stage*
- [ ] ➡️ Unified Kill Chain
- [ ] ⭐ MITRE — *the most important framework in defensive security; map every technique you encounter to ATT&CK from this point forward*
- [ ] ➡️ Summit
- [ ] ⚡ Eviction

### Section 5: Phishing Analysis
- [ ] ⭐ Phishing Analysis Fundamentals — *email header analysis is a direct examiner skill*
- [ ] ⭐ Phishing Emails in Action
- [ ] ⭐ Phishing Analysis Tools
- [ ] ➡️ Phishing Prevention
- [ ] ⭐ The Greenholt Phish — *treat this like a real case; document findings as if writing a report*
- [ ] ⭐ Snapped Phish-ing Line — *same*
- [ ] ⭐ Phishing Unfolding — *same*

### Section 6: Network Traffic Analysis
- [ ] ➡️ Network Traffic Basics
- [ ] ⚡ Wireshark: The Basics *(covered in Phase 2)*
- [ ] ⭐ Wireshark: Packet Operations — *filtering, following streams, extracting files from PCAP*
- [ ] ⭐ Wireshark: Traffic Analysis — *identifying C2 traffic, exfiltration patterns, anomalies*
- [ ] ⭐ NetworkMiner — *extracts files, credentials, and host artifacts directly from PCAP; this is a forensic tool, not just a monitoring tool*

### Section 7: Network Security Monitoring
- [ ] ➡️ Network Security Essentials
- [ ] ➡️ Network Discovery Detection
- [ ] ⭐ Data Exfiltration Detection — *exfiltration cases are one of the most common examiner scenarios; study the detection patterns, then ask: what artifacts prove this happened?*
- [ ] ➡️ Man-in-the-Middle Detection
- [ ] ⚡ IDS Fundamentals *(covered in Phase 2)*
- [ ] ➡️ Snort

### Section 8: Web Security Monitoring
- [ ] ➡️ Web Security Essentials
- [ ] ➡️ Detecting Web Attacks — *web server logs are a forensic artifact*
- [ ] ➡️ Detecting Web Shells
- [ ] ⚡ Detecting Web DDoS

### Section 9: Windows Security Monitoring
- [ ] ⭐ Windows Logging for SOC — *Windows artifact knowledge in disguise; every log source covered here is something you will parse as an examiner*
- [ ] ⭐ Windows Threat Detection 1 — *Windows Event IDs and Sysmon logs are core forensic evidence*
- [ ] ⭐ Windows Threat Detection 2 — *take notes on every Event ID covered*
- [ ] ⭐ Windows Threat Detection 3 — *by the end of this section you should know the key Event IDs cold*

### Section 10: Linux Security Monitoring
- [ ] ⭐ Linux Logging for SOC — *Linux log locations and formats are directly relevant to Linux forensics in Phase 4*
- [ ] ➡️ Linux Threat Detection 1
- [ ] ➡️ Linux Threat Detection 2
- [ ] ➡️ Linux Threat Detection 3

### Section 11: Malware Concepts for SOC
- [ ] ⭐ Malware Classification — *know the taxonomy: ransomware, RAT, rootkit, wiper, infostealer; you will classify malware in reports*
- [ ] ⭐ Intro to Malware Analysis — *safe triage workflow; feeds directly into Phase 4 and projects*
- [ ] ⭐ Living Off the Land Attacks — *LOLBins appear in almost every modern incident; know certutil, mshta, regsvr32, wmic, and PowerShell abuse patterns cold*
- [ ] ➡️ Shadow Trace

### Section 12: Threat Analysis Tools
- [ ] ➡️ Intro to Cyber Threat Intel
- [ ] ⭐ File and Hash Threat Intel — *VirusTotal and hash-based IOC lookups are part of every forensic report*
- [ ] ➡️ IP and Domain Threat Intel
- [ ] ➡️ Invite Only

### Section 13: SIEM Triage for SOC
- [ ] ⭐ Log Analysis with SIEM
- [ ] ⭐ Alert Triage With Splunk — *hands-on SPL*
- [ ] ⭐ Alert Triage With Elastic — *hands-on KQL*
- [ ] ➡️ ItsyBitsy
- [ ] ➡️ Benign

### Section 14: SOC Level 1 Capstone Challenges
- [ ] ➡️ Tempest
- [ ] ⭐ Boogeyman 1 — *treat this as a real investigation; write a full report for at least one of the three*
- [ ] ⭐ Boogeyman 2
- [ ] ⭐ Boogeyman 3 — *by the time you finish these your Phase 5 report writing will be dramatically cleaner*

---

## Week-by-Week Schedule

**Week 7 (July 11–17):** Sections 1–2 (SOC Fundamentals, Team Internals) → Section 3 (Splunk, Elastic, EDR) → Section 4 (Pyramid of Pain, Kill Chain, MITRE) → Section 5 (all Phishing rooms)

**Week 8 (July 18–24):** Section 6 (Wireshark deep pass, NetworkMiner) → Section 7 (Network Monitoring, Exfiltration Detection) → Sections 8–10 (Web, Windows, Linux Monitoring) → Section 11 (Malware — classification, LOLBins)

**Week 9 partial (July 25–29):** Section 12 (Threat Intel) → Section 13 (SIEM triage with Splunk and Elastic) → Section 14 (Capstones — Tempest, Boogeyman 1–3)

---

## Priority Rooms for a Forensic Examiner

**Windows Threat Detection 1–3** — Windows Event IDs and Sysmon logs are some of the most valuable artifacts in forensic investigation. Know these cold: 4624 (logon), 4625 (failed logon), 4648 (explicit credential logon), 4688 (process creation), 4697 (new service), 4720 (new user account), 7045 (new service installed).

**NetworkMiner** — Where Wireshark shows you packets, NetworkMiner extracts artifacts: files transferred, credentials transmitted, host details. This is the network forensics workflow.

**Data Exfiltration Detection** — Study the detection patterns from the SOC side, then flip the question: if you were the examiner, what artifacts would prove this happened? What registry keys, what event logs, what PCAP evidence?

**Boogeyman 1–3** — Treat these as forensic investigations. Write a full report for at least one of them using the schema from Phase 5. The report writing practice here directly reduces the learning curve on your portfolio projects.

**MITRE ATT&CK** — Map every technique you encounter throughout this phase to a tactic and technique at attack.mitre.org. Do this consistently from here forward. It will be the first thing interviewers ask you to demonstrate.

---

## References

- [MITRE ATT&CK Navigator](https://mitre-attack.github.io/attack-navigator/) — interactive heatmap; track every technique you encounter
- [Boss of the SOC (BOTS) Datasets](https://github.com/splunk/botsdatasets) — Splunk CTF dataset; practice SPL at enterprise scale
- [Any.run Interactive Sandbox](https://app.any.run/) — watch malware execute live and capture process and network artifacts
- [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures) — real PCAP files from infections, scans, and protocols
- [Windows Event Log Encyclopedia](https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/) — definitive reference for every Windows Event ID

---

*[← Phase 2](./02-cyber-security-101.md) | [Back to Roadmap](../README.md) | [Phase 4 →](./04-dfir-deep-dive.md)*
