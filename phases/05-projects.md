# Phase 5 — DFIR Projects & Portfolio
**Weeks 9–11 | July 28 – August 13 | ~40 hours | ~20 hrs/week**

---

## 🎯 Goal
Apply everything you've learned to real-world inspired DFIR projects. These projects solve realistic problems you would encounter as a forensic analyst. Each one becomes a portfolio piece for internships, jobs, and your GitHub profile.

---

## 📁 Project Overview

| # | Project | Focus Area | Difficulty | Est. Time |
|---|---------|------------|------------|-----------|
| 1 | **Ransomware Attack Investigation** | Disk + Memory + Network | ⭐⭐⭐ | ~12 hrs |
| 2 | **Insider Threat Investigation** | Disk forensics + OSINT | ⭐⭐ | ~8 hrs |
| 3 | **Phishing Campaign Forensics** | Email + Network + Endpoint | ⭐⭐ | ~8 hrs |
| 4 | **USB Exfiltration Forensics** | Windows artifacts + Timeline | ⭐⭐⭐ | ~10 hrs |

> Complete at minimum **Projects 1 and 2** before August 13. Do all 4 if pace allows.

---

## 🔬 Project 1: Ransomware Attack Investigation
**Folder:** `./project-01-ransomware/`

### Scenario
A Windows workstation at a small accounting firm was found encrypted. The IT admin preserved a disk image and a memory dump before rebuilding the system. You are the forensic analyst called in to determine what happened.

### Objectives
- [ ] Analyze the memory dump with Volatility — identify malicious processes
- [ ] Examine the disk image with Autopsy — find dropped malware artifacts
- [ ] Reconstruct the attack timeline (infection → persistence → encryption)
- [ ] Identify the ransomware family and likely infection vector
- [ ] Write a full forensic investigation report

### Resources to Use
- **Sample Memory Dumps:** [MemLabs](https://github.com/stuxnet999/MemLabs) — free CTF memory challenges
- **Practice Disk Images:** [Digital Corpora](https://digitalcorpora.org/) — free forensic datasets
- TryHackMe room: [Advent of Cyber Day 6 (any year)](https://tryhackme.com/room/adventofcyber2023) — ransomware investigation day

### Deliverables
```
project-01-ransomware/
├── README.md           ← Project description and methodology
├── findings.md         ← Your full forensic report
├── timeline.md         ← Attack timeline reconstruction
├── iocs.md             ← Indicators of Compromise found
└── screenshots/        ← Evidence screenshots
```

---

## 🔬 Project 2: Insider Threat Investigation
**Folder:** `./project-02-insider-threat/`

### Scenario
An employee at a tech company was terminated. Before leaving, they allegedly exfiltrated sensitive IP via USB and personal email. HR has preserved their workstation disk image. You must find evidence.

### Objectives
- [ ] Identify connected USB devices (Windows registry: USBSTOR)
- [ ] Recover file access history (LNK files, Recent Items, Shellbags)
- [ ] Analyze browser history for webmail exfiltration
- [ ] Check for cloud sync tools (Dropbox, Google Drive) activity
- [ ] Build a timeline of suspicious activity
- [ ] Write a litigation-ready incident report

### Resources to Use
- TryHackMe rooms: Windows Forensics 1 & 2 (revisit)
- **Practice dataset:** [NIST CFReDS](https://cfreds.nist.gov/) — official forensic reference datasets
- Tool: **Regripper** for registry parsing

### Deliverables
```
project-02-insider-threat/
├── README.md
├── findings.md         ← What evidence was found
├── timeline.md
├── usb_analysis.md     ← USB device registry findings
└── screenshots/
```

---

## 🔬 Project 3: Phishing Campaign Forensics
**Folder:** `./project-03-phishing-forensics/`

### Scenario
Several employees received phishing emails. One clicked a link and the endpoint was compromised. You have email samples, browser history, and endpoint logs.

### Objectives
- [ ] Analyze email headers to trace phishing origin
- [ ] Identify the malicious URL / payload from browser history
- [ ] Check Windows event logs for initial execution
- [ ] Use Wireshark to analyze C2 (command-and-control) traffic
- [ ] Map the attack to MITRE ATT&CK techniques
- [ ] Write a complete IR (Incident Response) report

### Resources to Use
- TryHackMe: [Phishing Analysis Fundamentals](https://tryhackme.com/room/phishingemails1tryoe)
- [PhishTool](https://www.phishtool.com/) — free email analysis
- [Any.run](https://app.any.run/) — free malware sandbox

### Deliverables
```
project-03-phishing-forensics/
├── README.md
├── email_analysis.md
├── iocs.md
├── mitre_mapping.md    ← MITRE ATT&CK techniques used
└── screenshots/
```

---

## 🔬 Project 4: USB Exfiltration Timeline Forensics
**Folder:** `./project-04-usb-timeline/`

### Scenario
A data breach is suspected. A forensic image of a suspect's Windows 10 machine was acquired. Your job is to create a complete forensic timeline of activity and prove data was moved to external storage.

### Objectives
- [ ] Use **Plaso / log2timeline** to create a full system timeline
- [ ] Filter timeline to identify USB connection events
- [ ] Cross-reference with file access and deletion artifacts
- [ ] Identify any anti-forensics (Evidence of tampering, wiping)
- [ ] Export and present the timeline as a visual artifact

### Tools
- **Plaso** — timeline supertool (`pip install plaso`)
- **Timeline Explorer** (Eric Zimmerman) — free Windows timeline viewer

### Deliverables
```
project-04-usb-timeline/
├── README.md
├── methodology.md
├── timeline_export.csv
├── findings.md
└── screenshots/
```

---

## 📋 How to Write a Forensic Report

Every project report should include these sections:

```markdown
# Forensic Investigation Report

## 1. Executive Summary
(2-3 sentences — what happened, what was found)

## 2. Scope & Methodology
(What systems, what tools, what timeframe)

## 3. Findings
(Detailed, factual, chronological)

## 4. Evidence
(SHA-256 hashes, file paths, screenshots)

## 5. Timeline of Events
(Timestamped chronology)

## 6. Indicators of Compromise (IOCs)
(IPs, hashes, file names, registry keys)

## 7. MITRE ATT&CK Mapping
(Tactic → Technique → Sub-technique)

## 8. Conclusions & Recommendations
(What happened, what to fix)

## 9. Analyst Certification
(Your name, date, statement of objectivity)
```

---

## 🌐 Additional Practice Platforms

When you need more challenges beyond TryHackMe:

| Platform | Free? | Best For |
|----------|-------|----------|
| [CyberDefenders](https://cyberdefenders.org/) | ✅ Free | Blue team + DFIR CTFs |
| [BlueTeamLabs Online](https://blueteamlabs.online/) | ✅ Free tier | SOC + forensics |
| [MemLabs](https://github.com/stuxnet999/MemLabs) | ✅ Free | Memory forensics CTF |
| [NIST CFReDS](https://cfreds.nist.gov/) | ✅ Free | Real forensic datasets |
| [Digital Corpora](https://digitalcorpora.org/) | ✅ Free | Disk images for practice |
| [HackTheBox (Forensics)](https://app.hackthebox.com/challenges) | ✅ Free tier | Hard DFIR challenges |

---

## 🏆 Final Milestones (Aug 13 Deadline)
- [ ] Complete Project 1 (Ransomware) — full report written
- [ ] Complete Project 2 (Insider Threat) — full report written
- [ ] Start or complete Projects 3 and/or 4
- [ ] Push all projects to your GitHub with clean README files
- [ ] LinkedIn: update your profile to include DFIR skills + link GitHub
- [ ] Write a reflection post in `progress-tracker/tracker.md`

---

[← Phase 4](./04-digital-forensics-deep-dive.md) | [Back to Roadmap](../README.md)
