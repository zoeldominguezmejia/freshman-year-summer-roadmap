# Phase 4 — Digital Forensics Foundations
**Timeline: July 30 – August 12 | ~40 hours | ~20 hrs/week**

---

## Overview

This phase develops the core technical skills of a working digital forensics examiner. Every room maps directly to a tool category used professionally. The goal is to move beyond tool usage and into forensic methodology — understanding not just *how* to use Volatility, but *what* each plugin reveals, *when* you would use it, and *how* you document the findings in a legally defensible report.

By the end of this phase, you should be able to: conduct a disk forensic examination in Autopsy, perform memory analysis with Volatility 3, triage a system with KAPE, parse Windows artifacts with the Eric Zimmerman tool suite, and produce a professional forensic report from scratch.

---

## Room Checklist

> **Pace guide:** ⭐ = go slow, take full notes | ➡️ = normal pace | ⚡ = complete it, move on

### Forensic Foundations & Windows Artifacts
- [ ] ⭐ DFIR: An Introduction — *the six-phase methodology is the framework for every examination you will ever conduct; know it without thinking*
- [ ] ⭐ Windows Forensics 1 — *registry hive locations, UserAssist, ShimCache, AmCache, MUICache; take meticulous notes including exact registry key paths*
- [ ] ⭐ Windows Forensics 2 — *Prefetch, LNK files, Jump Lists, Shellbags, browser artifacts, Recycle Bin; same level of note-taking*

### Linux Forensics
- [ ] ⭐ Linux Forensics — *log locations, bash history, cron jobs, passwd and shadow files, file system timestamps*

### Disk Forensics
- [ ] ⭐ Autopsy — *your primary free examination platform; get genuinely comfortable with the interface, not just familiar with it*

### Endpoint & Memory Triage
- [ ] ➡️ Redline — *useful tool; Volatility is where you will spend more time in real casework*
- [ ] ⭐ KAPE — *rapid artifact collection without full imaging; know the difference between Targets and Modules and why it matters in time-sensitive response*
- [ ] ⭐ Volatility — *the hardest and most differentiating skill in this roadmap; go slower here than anywhere else*
- [ ] ➡️ Velociraptor — *enterprise-scale tool worth understanding conceptually*

### Case Management
- [ ] ➡️ TheHive Project — *understand the workflow; documentation habits matter more than the specific tool*

### Malware Analysis
- [ ] ⭐ Intro to Malware Analysis — *safe triage workflow for suspected malware; understand the static and dynamic analysis distinction*

### Capstone Investigations
- [ ] ⭐ Unattended — *treat this as a real case, not a CTF; write a full forensic report using the Phase 5 schema*
- [ ] ⭐ Disgruntled — *same standard; Linux forensics applied to a real scenario*
- [ ] ➡️ Critical — *solid memory forensics practice; apply Volatility skills*
- [ ] ⭐ Secret Recipe — *registry forensics case; the artifact hunting directly mirrors project work*

---

## Week-by-Week Schedule

**Week 10 (July 30 – August 5):** DFIR Introduction → Windows Forensics 1 → Windows Forensics 2 → Linux Forensics → Autopsy. Take detailed notes on every artifact location: registry hive paths, file system structures, log file locations, browser artifact paths. Begin setting up your local forensics VM.

**Week 11 (August 6–12):** Redline → KAPE → Volatility → Velociraptor → TheHive → Intro to Malware Analysis → Capstones (Unattended, Disgruntled, Critical, Secret Recipe). Document methodology, tools, and findings for every capstone. These become your Phase 5 report templates.

---

## Priority Rooms for a Forensic Examiner

**DFIR: An Introduction** — The six-phase methodology is not optional: Identification → Preservation → Collection → Examination → Analysis → Reporting. Every professional examination follows this sequence. It is the first thing you say in an interview when asked to walk through an investigation.

**Windows Forensics 1 and 2** — The artifact categories covered here are the foundation of most corporate forensic cases. Take meticulous notes on exact registry key paths and file system locations. These do not change and you will reference them constantly.

**Volatility** — Memory forensics is what differentiates candidates. Know these plugins cold:
- `windows.pslist` / `windows.pstree` — running processes and parent-child relationships
- `windows.cmdline` — command-line arguments passed to each process
- `windows.netscan` — active and recently closed network connections
- `windows.malfind` — memory regions with suspicious characteristics (injected code)
- `windows.dlllist` — loaded DLLs per process (spot hijacked or injected DLLs)
- `windows.handles` — open handles to files, registry keys, and mutexes

**KAPE** — Rapid triage tool used in real enterprise IR. Understanding KAPE Targets and Modules directly maps to how you scope artifact collection in a real case. Collecting the right artifacts quickly without full imaging is a genuinely valuable skill in time-sensitive response.

**Unattended and Disgruntled** — The closest rooms in the entire module to real casework. Write a full forensic report for both using the Phase 5 report schema. Do not treat them as CTF boxes.

---

## Local Forensics Environment Setup

Build this before Phase 5 begins. TryHackMe's AttackBox handles in-browser labs, but you need a local environment for portfolio projects.

```bash
# On Kali Linux
sudo apt update && sudo apt install -y autopsy sleuthkit foremost tshark wireshark

# Volatility 3
pip3 install volatility3

# Eric Zimmerman Tools (Windows) — mandatory for Windows artifact analysis
# Full suite: https://ericzimmerman.github.io/
# Priority: MFTECmd, PECmd, LECmd, JLECmd, ShellBags Explorer, Registry Explorer, RECmd, Timeline Explorer

# FTK Imager (free, Windows)
# https://www.exterro.com/ftk-imager

# KAPE (Windows)
# https://www.kroll.com/en/services/cyber-risk/incident-response-litigation-support/kroll-artifact-parser-extractor-kape

# Magnet AXIOM — request 30-day trial
# https://www.magnetforensics.com/products/magnet-axiom/

# REMnux — Linux malware analysis VM
# https://remnux.org/
```

---

## Forensic Examination Methodology

Every examination follows this sequence without exception.

```
1. IDENTIFICATION   → What incident occurred? What systems are potentially involved?
2. PRESERVATION     → Image the disk and memory before any other action.
                      Calculate and record MD5 + SHA-256 hashes of all evidence.
                      Never work on original evidence.
3. COLLECTION       → Gather artifacts: registry hives, event logs, prefetch, browser
                      history, LNK files, shellbags, USB artifacts, MFT, SRUM database.
4. EXAMINATION      → Parse artifacts: Autopsy, Volatility, KAPE, EZ Tools, Regripper.
5. ANALYSIS         → Build the timeline. Map behaviors to MITRE ATT&CK. Answer:
                      who, what, when, where, and how.
6. REPORTING        → Document all findings with artifact paths, hashes, screenshots,
                      and timestamps. Every claim must be supported by documented
                      evidence. Write for an audience that may include a judge or jury.
```

## Evidence Integrity — Non-Negotiables

- **Never examine original evidence.** Always work on a verified forensic copy.
- **Hash everything, every time.** MD5 and SHA-256 at acquisition and again before examination.
- **Document every action.** Tool name, version, command used, date, time, output produced.
- **Maintain chain of custody.** Record who has had access to the evidence and when.
- **Write for a non-technical reader.** Reports will be read by attorneys, HR, or judges. Define every technical term.

---

## References

- [13Cubed YouTube Channel](https://www.youtube.com/@13Cubed) — best free DFIR video content available; watch alongside every Windows forensics and Volatility room
- [Volatility 3 Plugin Reference](https://github.com/volatilityfoundation/volatility3)
- [SANS Windows Forensic Analysis Poster](https://www.sans.org/posters/windows-forensic-analysis/) — visual map of every registry key, prefetch file, and event log that records user activity
- [Digital Corpora](https://digitalcorpora.org/) — free realistic disk images and memory dumps
- [Magnet Forensics CTF Archives](https://www.magnetforensics.com/blog/) — annual forensic CTF images with writeups
- [SWGDE Documents](https://www.swgde.org/documents/published)

---

*[← Phase 3](./03-soc-level-1.md) | [Back to Roadmap](../README.md) | [Phase 5 →](./05-projects.md)*
