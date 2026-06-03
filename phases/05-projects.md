# Phase 5 — DFIR Projects & Professional Portfolio
**Timeline: August 12 – August 16 (start) | Continue through first weeks of semester**
**Hours: ~40 hours total | Projects 1 and 2 must be complete before August 17**

---

## 🎯 Goal
Apply everything from Phases 1–4 to real-world DFIR investigations. Each project produces a forensic report that goes directly on your GitHub and becomes the primary evidence of your skills when applying for internships and helpdesk roles. Employers will read these reports.

---

## 📁 Project Overview

| # | Project | Focus Area | Difficulty | Est. Time |
|---|---------|------------|------------|-----------|
| 1 | **Ransomware Attack Investigation** | Disk + Memory + Network | ⭐⭐⭐ | ~12 hrs |
| 2 | **Insider Threat Investigation** | Windows Artifacts + Registry | ⭐⭐ | ~8 hrs |
| 3 | **Phishing Campaign Forensics** *(Fall semester)* | Email + Endpoint + Network | ⭐⭐ | ~10 hrs |
| 4 | **USB Exfiltration Timeline Analysis** *(Spring semester)* | Timeline + Anti-Forensics | ⭐⭐⭐ | ~12 hrs |

Complete Projects 1 and 2 before August 17. Projects 3 and 4 are scheduled during the semester.

---

## 🔬 Project 1: Ransomware Attack Investigation
**Folder:** `./project-01-ransomware/`

### Scenario
A Windows workstation at a small accounting firm was found encrypted. The IT admin preserved a disk image and a memory dump before rebuilding the system. You are the forensic analyst called in to determine what happened.

### Objectives
- [ ] Analyze the memory dump with Volatility — identify malicious processes using windows.pslist, windows.cmdline, windows.malfind, and windows.netscan
- [ ] Examine the disk image with Autopsy — find dropped malware artifacts, modified files, and persistence mechanisms
- [ ] Reconstruct the attack timeline from infection to persistence to encryption
- [ ] Identify the ransomware family and likely infection vector
- [ ] Map the full attack chain to MITRE ATT&CK
- [ ] Write a complete forensic investigation report

### Resources
- **MemLabs:** [github.com/stuxnet999/MemLabs](https://github.com/stuxnet999/MemLabs) — Free CTF memory dumps for practice
- **Digital Corpora:** [digitalcorpora.org](https://digitalcorpora.org/) — Free forensic disk images
- **TryHackMe:** Advent of Cyber Day 6 — ransomware investigation scenario
- **MalwareBazaar:** [bazaar.abuse.ch](https://bazaar.abuse.ch/) — Real malware samples for safe-environment study

### Deliverables
```
project-01-ransomware/
├── README.md           ← Project description and methodology
├── findings.md         ← Full forensic report
├── timeline.md         ← Attack timeline reconstruction
├── iocs.md             ← Indicators of Compromise
└── screenshots/        ← Evidence screenshots with captions
```

---

## 🔬 Project 2: Insider Threat Investigation
**Folder:** `./project-02-insider-threat/`

### Scenario
An employee at a tech company was terminated. Before leaving, they allegedly exfiltrated sensitive IP via USB and personal email. HR has preserved their workstation disk image. You must find evidence.

### Objectives
- [ ] Identify connected USB devices using the Windows registry key USBSTOR
- [ ] Recover file access history from LNK files, Recent Items, and Shellbags
- [ ] Analyze browser history for webmail exfiltration (look for Gmail, Outlook Web, Dropbox uploads)
- [ ] Check for cloud sync tool activity (Dropbox, Google Drive, OneDrive)
- [ ] Build a complete timeline of suspicious activity
- [ ] Write a litigation-ready incident report suitable for HR or legal proceedings

### Resources
- **TryHackMe:** Windows Forensics 1 and 2 (revisit with investigation mindset)
- **NIST CFReDS:** [cfreds.nist.gov](https://cfreds.nist.gov/) — Official forensic reference datasets
- **Regripper:** Registry parsing tool
- **Eric Zimmerman Tools:** Full suite including ShellBags Explorer, JumpList Explorer, and LECmd for LNK file analysis

### Deliverables
```
project-02-insider-threat/
├── README.md
├── findings.md         ← What evidence was found, chain of custody
├── timeline.md         ← Chronological activity reconstruction
├── usb_analysis.md     ← USB device registry findings and timestamps
└── screenshots/
```

---

## 🔬 Project 3: Phishing Campaign Forensics
**Folder:** `./project-03-phishing/`
**Scheduled:** September – October 2026 (Fall semester)

### Scenario
Several employees received phishing emails. One clicked a link and the endpoint was compromised. You have email samples, browser history, and endpoint logs.

### Objectives
- [ ] Analyze email headers to trace the phishing origin — document SPF, DKIM, and DMARC failures
- [ ] Identify the malicious URL and payload from browser history
- [ ] Detonate a sample in Any.run sandbox — capture C2 traffic, dropped files, and process tree
- [ ] Check Windows event logs for initial execution artifacts
- [ ] Use Wireshark to analyze C2 communication patterns
- [ ] Map the full attack to MITRE ATT&CK: T1566.001 → T1059 → T1071
- [ ] Write a complete IR report

### Resources
- **PhishTool:** [phishtool.com](https://www.phishtool.com/) — Free email analysis
- **Any.run:** [app.any.run](https://app.any.run/) — Free malware sandbox
- **MXToolbox:** [mxtoolbox.com](https://mxtoolbox.com/) — Email header analysis and SPF/DKIM/DMARC checking
- **URLScan.io:** [urlscan.io](https://urlscan.io/) — URL reputation and screenshot analysis

### Deliverables
```
project-03-phishing/
├── README.md
├── email_analysis.md   ← Header analysis, SPF/DKIM/DMARC findings
├── iocs.md
├── mitre_mapping.md    ← Full ATT&CK chain
└── screenshots/
```

---

## 🔬 Project 4: USB Exfiltration Timeline Analysis
**Folder:** `./project-04-usb-timeline/`
**Scheduled:** February – March 2027 (Spring semester)

### Scenario
A data breach is suspected. A forensic image of a suspect's Windows 10 machine was acquired. Build a complete forensic timeline and prove data was moved to external storage.

### Objectives
- [ ] Use Plaso and log2timeline to build a full supertimeline from a Windows forensic image
- [ ] Filter the timeline to identify USB connection events
- [ ] Extract USB artifacts: USBSTOR registry key, setupapi.dev.log, and LNK files
- [ ] Cross-reference registry connection timestamps with file access timestamps
- [ ] Identify anti-forensics evidence — CCleaner runs, deleted VSS copies, timestamp manipulation
- [ ] Export the timeline as CSV and analyze in Timeline Explorer
- [ ] Write a litigation-ready report with SHA-256 hashes for every artifact

### Resources
- **NIST CFReDS or Digital Corpora** — Source image for the investigation
- **Plaso:** `pip install plaso` — Timeline supertool
- **Timeline Explorer:** [ericzimmerman.github.io](https://ericzimmerman.github.io/) — Free Windows timeline viewer

### Deliverables
```
project-04-usb-timeline/
├── README.md
├── methodology.md      ← Tools used and collection approach
├── timeline_export.csv ← Filtered Plaso output
├── findings.md
└── screenshots/
```

---

## 📋 Forensic Report Schema

Every report follows this structure. Do not deviate from it.

```markdown
# Forensic Investigation Report

## 1. Executive Summary
2–3 sentences: what happened, what was found, what is the conclusion.

## 2. Scope & Methodology
What system was examined. What tools were used. What timeframe was covered.
Include MD5 and SHA-256 hashes of all evidence files examined.

## 3. Findings
Detailed, factual, chronological. No speculation — only what the evidence shows.

## 4. Evidence
File paths, registry key locations, SHA-256 hashes, screenshots with timestamps.

## 5. Timeline of Events
Timestamped chronology from earliest artifact to last known activity.

## 6. Indicators of Compromise (IOCs)
IP addresses, domain names, file hashes, file names, registry keys, user agents.

## 7. MITRE ATT&CK Mapping
Tactic → Technique → Sub-technique for every observed behavior.
Reference: https://attack.mitre.org

## 8. Conclusions & Recommendations
What happened based on the evidence. What should be fixed or changed.

## 9. Analyst Certification
Your name, date of report, and a statement that the findings are accurate to the best of your knowledge.
```

---

## 🌐 Practice Platforms Beyond TryHackMe

| Platform | Free? | Best For |
|----------|-------|----------|
| [CyberDefenders](https://cyberdefenders.org/) | ✅ Free | Blue team + DFIR CTFs — do 1 per week during semester |
| [BlueTeamLabs Online](https://blueteamlabs.online/) | ✅ Free tier | SOC + forensics |
| [MemLabs](https://github.com/stuxnet999/MemLabs) | ✅ Free | Memory forensics CTF |
| [NIST CFReDS](https://cfreds.nist.gov/) | ✅ Free | Real forensic reference datasets |
| [Digital Corpora](https://digitalcorpora.org/) | ✅ Free | Disk images for practice |
| [HackTheBox Forensics](https://app.hackthebox.com/challenges) | ✅ Free tier | Hard DFIR challenges |

---

## 🏆 Milestones

### Before August 17 (classes start)
- [ ] Project 1 (Ransomware) complete — full report written and pushed to GitHub
- [ ] Project 2 (Insider Threat) complete — full report written and pushed to GitHub
- [ ] All project folders have clean README files
- [ ] LinkedIn updated: DFIR skills, all certs earned, GitHub link
- [ ] LinkedIn headline updated to reflect current cert stack

### Fall 2026
- [ ] Project 3 (Phishing) complete — September through October

### Spring 2027
- [ ] Project 4 (USB Timeline) complete — February through March

---

*[← Phase 4](./04-dfir-deep-dive.md) | [Back to Main Roadmap](../README.md)*
