# Phase 5 — DFIR Projects & Professional Portfolio
**Timeline: August 10 – August 16 | ~40 hours | ~20 hrs/week**

---
🎯 Goal

Apply everything you've learned to real-world inspired DFIR projects. These projects solve realistic problems you would encounter as a forensic analyst. Each one becomes a portfolio piece for internships, jobs, and your GitHub profile.

---

## 📁 Project Overview

| #   | Project | Focus Area | Difficulty | Est. Time |
| --- | --- | --- | --- | --- |
| 1   | **Ransomware Attack Investigation** | Disk + Memory + Network | ⭐⭐⭐ | ~12 hrs |
| 2   | **Insider Threat Investigation** | Disk forensics + OSINT | ⭐⭐  | ~8 hrs |

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
| --- | --- | --- |
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

*[← Phase 4](./04-dfir-deep-dive.md) | [Back to Main Roadmap](../README.md)*
