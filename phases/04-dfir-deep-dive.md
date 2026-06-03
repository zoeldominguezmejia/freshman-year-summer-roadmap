# Phase 4 — Digital Forensics Examiner Deep Dive & Google Certificate Graduation
**Timeline: July 30 – August 12 | ~40 hours | ~20 hrs/week**
---

## 🎯 Goal
Develop the core technical skills of a working digital forensics examiner. Every room in this phase maps directly to a tool category you will use professionally. The standard you are holding yourself to is not "complete the lab" — it is "could I defend these findings in a written report?" Complete the Google Cybersecurity Certificate during this phase.

---

## 📚 Dual-Platform Alignment

### 1. TryHackMe: Digital Forensics and Incident Response Module
The official THM DFIR track. Covers Windows and Linux forensic artifacts, memory analysis, disk forensics, rapid triage, endpoint monitoring, case management, and malware analysis fundamentals.

### 2. UNCC Coursera: Google Cybersecurity Certificate — Final Module
Complete Module 8 (career preparation, portfolio building, interview prep) and claim your verified professional certificate.

---

## ✅ Full Room Checklist

### Forensic Foundations & Windows Artifacts
- [ ] DFIR: An Introduction ⭐ *(methodology framework for every examination you will ever conduct)*
- [ ] Windows Forensics 1 ⭐ — Windows Registry forensics
- [ ] Windows Forensics 2 ⭐ — Windows file systems and file system artifacts

### Linux Forensics
- [ ] Linux Forensics ⭐ — Forensic artifacts in the Linux file system

### Disk Forensics
- [ ] Autopsy ⭐ — Full disk forensics with Autopsy (employee data leak case)

### Endpoint & Memory Triage
- [ ] Redline — Endpoint memory analysis and IOC scanning (Mandiant)
- [ ] KAPE ⭐ — Rapid artifact collection without full disk imaging
- [ ] Volatility ⭐ — Memory forensics framework (the hardest skill in DFIR — spend the most time here)
- [ ] Velociraptor — Advanced endpoint monitoring and forensic response platform

### Case Management
- [ ] TheHive Project — Security Incident Response Platform for documenting findings

### Malware Analysis
- [ ] Intro to Malware Analysis ⭐ — Safe triage workflow for suspected malware

### Capstone Investigations
- [ ] Unattended ⭐ — Windows forensics investigation: apply everything from Windows Forensics 1 & 2
- [ ] Disgruntled ⭐ — Linux forensics investigation: apply Linux forensics knowledge
- [ ] Critical — Memory dump analysis in a practical scenario
- [ ] Secret Recipe ⭐ — Registry forensics case

### UNCC Coursera — Google Cybersecurity Certificate
- [ ] Module 7: Automate Cybersecurity Tasks with Python *(complete if not finished in Phase 3)*
- [ ] Module 8: Put It to Work — Prepare for Cybersecurity Jobs
- [ ] **MILESTONE: Claim Google Cybersecurity Professional Certificate**

---

## 📝 Phase 4 Schedule

### Week 10 (July 30 – August 5) — Foundations, Windows, Linux, Disk
- TryHackMe: DFIR Introduction → Windows Forensics 1 → Windows Forensics 2 → Linux Forensics → Autopsy
- Take detailed notes on every artifact location: registry hive paths, file system structures, log file locations, browser artifact paths.
- Begin setting up your local forensics VM.
- Coursera: Complete Google Module 7 if not done. Begin Module 8.

### Week 11 (August 6 – August 12) — Memory, Triage, Malware, Capstones
- TryHackMe: Redline → KAPE → Volatility → Velociraptor → TheHive → Intro to Malware Analysis
- TryHackMe: Capstone rooms — Unattended, Disgruntled, Critical, Secret Recipe
- Document methodology, tools, and findings for every capstone in Obsidian or markdown. These become your Phase 5 templates.
- Coursera: Complete Module 8. Claim your Google Cybersecurity Professional Certificate. Post the badge on LinkedIn the same day.
- **Milestone:** All Phase 4 rooms complete. Scope Phase 5 projects.

---

## ⭐ Priority Rooms for a Forensic Examiner

**DFIR: An Introduction** — The six-phase methodology is not optional: Identification → Preservation → Collection → Examination → Analysis → Reporting. Every professional examination follows this sequence. It is also the first thing you say in any interview when asked to walk through an investigation. Know it without thinking.

**Windows Forensics 1 and 2** — The artifact categories covered here are the foundation of most corporate forensic cases: registry hives (SAM, SYSTEM, SOFTWARE, NTUSER.DAT), UserAssist, ShimCache, AmCache, MUICache, Shellbags, Prefetch, LNK files, Jump Lists, browser artifacts, and the Recycle Bin. Take meticulous notes including the exact registry key paths and file system locations. You will be hunting these in Projects 2 and 4.

**Volatility** — Memory forensics is what differentiates candidates. Know these plugins cold and understand what each reveals:
  - `windows.pslist` / `windows.pstree` — running processes and parent-child relationships
  - `windows.cmdline` — command-line arguments passed to each process
  - `windows.netscan` — active and recently closed network connections
  - `windows.malfind` — memory regions with suspicious characteristics (injected code)
  - `windows.dlllist` — loaded DLLs per process (spot hijacked or injected DLLs)
  - `windows.handles` — open handles (files, registry keys, mutexes)

**KAPE** — Rapid triage tool used in real enterprise IR. KAPE collects the right artifacts without imaging an entire disk, which is critical in time-sensitive response scenarios. Understanding KAPE Targets and Modules directly maps to how you would scope artifact collection in a real case.

**Unattended and Disgruntled** — These are the closest rooms in the entire module to a real casework scenario. Write a full forensic report for both using the Phase 5 schema. Do not treat them as CTF boxes. By the time you finish these reports, you should be able to produce professional investigation documentation from scratch.

---

## 🧰 Tool Setup — Local Forensics Environment

Build this before Phase 5 begins. The TryHackMe AttackBox handles in-browser labs, but you need a local environment for your portfolio projects.

```bash
# On Kali Linux
sudo apt update && sudo apt install -y autopsy sleuthkit foremost tshark wireshark

# Volatility 3
pip3 install volatility3

# KAPE — Windows only
# Download from: https://www.kroll.com/en/services/cyber-risk/incident-response-litigation-support/kroll-artifact-parser-extractor-kape

# Eric Zimmerman Tools (Windows) — mandatory for Windows artifact analysis
# Full suite: https://ericzimmerman.github.io/
# Priority tools: MFTECmd, PECmd, LECmd, JLECmd, ShellBags Explorer, Registry Explorer, RECmd, Timeline Explorer

# FTK Imager (free, Windows)
# Download from: https://www.exterro.com/ftk-imager

# Magnet AXIOM — request a 30-day trial
# https://www.magnetforensics.com/products/magnet-axiom/

# REMnux — dedicated Linux malware analysis VM
# Download from: https://remnux.org/
```

---

## 📋 Forensic Examination Methodology Reference

Every examination follows this workflow without exception.

```
1. IDENTIFICATION   → What incident occurred? What systems are potentially involved?
2. PRESERVATION     → Image the disk (FTK Imager) and memory dump before any other action.
                      Calculate and record MD5 + SHA-256 hashes of all evidence.
                      Never work on original evidence — always work on verified copies.
3. COLLECTION       → Gather artifacts: registry hives, event logs, prefetch, browser history,
                      LNK files, shellbags, USB artifacts, MFT, SRUM database.
4. EXAMINATION      → Parse artifacts with tools: Autopsy, Volatility, KAPE, EZ Tools, Regripper.
5. ANALYSIS         → Build the timeline. Map behaviors to MITRE ATT&CK. Identify TTPs.
                      Answer: who, what, when, where, and how.
6. REPORTING        → Document all findings with artifact paths, SHA-256 hashes, screenshots,
                      and timestamps. Every claim must be supported by documented evidence.
                      Write for an audience that may include a judge or jury.
```

---

## ⚖️ Evidence Integrity — The Non-Negotiables

These are not best practices. They are professional requirements. Begin treating them as mandatory now.

- **Never examine original evidence.** Always work on a verified forensic copy.
- **Hash everything, every time.** Calculate MD5 and SHA-256 at acquisition and again before examination. If the hashes match, the evidence is unmodified.
- **Document every action you take.** If you ran a tool against the evidence, write it down: tool name, version, command or configuration used, date and time, and what output was produced.
- **Maintain chain of custody.** Record who has had access to the evidence and when.
- **Write for a non-technical reader.** Your report will be read by attorneys, HR departments, or judges. Define every technical term you use.

---

## 🔗 Supplemental Resources

- **13Cubed YouTube Channel:** [youtube.com/@13Cubed](https://www.youtube.com/@13Cubed) — Best free DFIR video content available. Watch alongside every Windows forensics and Volatility room.
- **Volatility 3 Plugin Reference:** [GitHub](https://github.com/volatilityfoundation/volatility3) — Authoritative plugin documentation.
- **SANS Windows Forensic Analysis Poster:** [sans.org/posters](https://www.sans.org/posters/windows-forensic-analysis/) — Visual map of every registry key, prefetch file, and event log that records user activity. Print it.
- **Digital Corpora:** [digitalcorpora.org](https://digitalcorpora.org/) — Free realistic disk images and memory dumps.
- **Magnet Forensics CTF Archives:** [magnetforensics.com/blog](https://www.magnetforensics.com/blog/) — Magnet releases forensic CTF images annually with writeups. Excellent real-world practice.
- **SWGDE Documents:** [swgde.org](https://www.swgde.org/documents/published) — Professional standards every examiner is expected to know.

---

*[← Phase 3](./03-soc-level-1.md) | [Back to Main Roadmap](../README.md) | [Phase 5 →](./05-projects.md)*
