# Phase 4 — Digital Forensics Deep Dive & Google Certificate Graduation
**Timeline: July 29 – August 11 | ~40 hours | ~20 hrs/week**

---

## 🎯 Goal
Develop deep, specialized proficiency with the core tools and techniques used by professional digital forensic examiners. This is the official TryHackMe DFIR module — every room feeds directly into your Phase 5 portfolio projects. Complete the Google Cybersecurity Certificate during this phase.

---

## 📚 Dual-Platform Alignment

### 1. TryHackMe: Digital Forensics and Incident Response Module
The official THM DFIR track. Covers Windows and Linux forensic artifacts, memory analysis with Volatility, disk forensics with Autopsy, triage with KAPE, endpoint monitoring with Velociraptor, case management with TheHive, and malware analysis fundamentals.

### 2. UNCC Coursera: Google Cybersecurity Certificate — Final Module
Complete Module 8 (career preparation, portfolio building, interview prep) and claim your verified professional certificate badge.

---

## ✅ Full Room Checklist

### Forensic Foundations & Windows Artifacts
- [ ] DFIR: An Introduction ⭐ *(start here — sets the methodology framework for everything else)*
- [ ] Windows Forensics 1 ⭐ — Windows Registry forensics
- [ ] Windows Forensics 2 ⭐ — Windows file systems and file system artifacts

### Linux Forensics
- [ ] Linux Forensics ⭐ — Forensic artifacts in the Linux file system

### Disk Forensics
- [ ] Autopsy ⭐ — Full disk forensics investigation with Autopsy (employee data leak case)

### Endpoint & Memory Triage
- [ ] Redline — Memory analysis and IOC scanning on an endpoint
- [ ] KAPE ⭐ — Kroll Artifact Parser and Extractor for rapid artifact collection
- [ ] Volatility ⭐ — Memory forensics framework (core skill — spend extra time here)
- [ ] Velociraptor — Advanced endpoint monitoring and digital forensic response platform

### Case Management
- [ ] TheHive Project — Security Incident Response Platform for documenting investigation findings

### Malware Analysis
- [ ] Intro to Malware Analysis ⭐ — What to do when you encounter suspected malware

### Capstone Investigations
- [ ] Unattended ⭐ — Apply Windows forensics knowledge to investigate a real incident
- [ ] Disgruntled ⭐ — Apply Linux forensics knowledge to investigate a real incident
- [ ] Critical — Memory dump analysis in a practical scenario
- [ ] Secret Recipe ⭐ — Registry forensics investigation case

### UNCC Coursera — Google Cybersecurity Certificate
- [ ] Module 7: Automate Cybersecurity Tasks with Python *(finish if not done in Phase 3)*
- [ ] Module 8: Put It to Work — Prepare for Cybersecurity Jobs
- [ ] **MILESTONE: Claim Google Cybersecurity Professional Certificate badge**

---

## 📝 Phase 4 Schedule

### Week 10 (July 29 – August 4) — Focus: Foundations, Windows, Linux, Disk
- TryHackMe: DFIR Introduction → Windows Forensics 1 → Windows Forensics 2 → Linux Forensics → Autopsy
- This week establishes your artifact knowledge base. Take detailed notes on registry keys, file system structures, and artifact locations — you will reference these constantly in Phase 5.
- Coursera: Complete Google Module 7 (Python automation) if not finished in Phase 3. Begin Module 8.

### Week 11 (August 5 – August 11) — Focus: Memory, Triage, Malware, Capstones
- TryHackMe: Redline → KAPE → Volatility → Velociraptor → TheHive → Intro to Malware Analysis
- TryHackMe: Capstone investigations — Unattended, Disgruntled, Critical, Secret Recipe
- Treat each capstone as a real case. Document your methodology, tools used, and findings in Obsidian or a markdown file. These notes directly become your Phase 5 report templates.
- Coursera: Complete Module 8 and claim your Google Cybersecurity Professional Certificate. Post the badge on LinkedIn the same day.
- **Milestone:** All Phase 4 rooms complete. Begin scoping Phase 5 projects.

---

## ⭐ Priority Rooms to Slow Down On

**DFIR: An Introduction** — Sets the methodology you use for every investigation: Identification → Preservation → Collection → Examination → Analysis → Reporting. Know this cold. It is the first thing you say in an interview when asked to walk through an investigation.

**Volatility** — Memory forensics is the hardest DFIR skill to learn and the one that most differentiates candidates. Spend extra time here. Know these plugins cold: windows.pslist, windows.pstree, windows.cmdline, windows.netscan, windows.malfind, windows.dlllist. Understand what each reveals and when you would use it.

**Windows Forensics 1 and 2** — Registry hive locations, UserAssist, ShimCache, MUICache, Shellbags, LNK files, Jump Lists, browser artifacts. These are the artifacts you will hunt in Projects 2 and 4.

**KAPE** — Rapid triage tool used in real enterprise incident response. Understanding KAPE targets and modules lets you collect the right artifacts without imaging an entire disk. Very commonly asked about in DFIR interviews.

**Unattended and Disgruntled** — These are the closest rooms to a real investigation scenario in the entire module. Write a full forensic report for both using the Phase 5 schema. By the time you finish these, you should be able to produce a professional investigation report from scratch.

---

## 🧰 Tools to Have Ready Before Phase 5

Install these on Kali Linux or a dedicated forensics VM. If you do not want to set up a local VM, the TryHackMe AttackBox handles all in-browser labs.

```bash
# On Kali Linux
sudo apt install autopsy sleuthkit foremost volatility3 wireshark

# KAPE — Windows only, download from Kroll
# https://www.kroll.com/en/services/cyber-risk/incident-response-litigation-support/kroll-artifact-parser-extractor-kape

# Eric Zimmerman Tools — Windows forensics suite
# https://ericzimmerman.github.io/

# REMnux — dedicated Linux VM for malware analysis
# https://remnux.org/
```

---

## 📋 Forensic Investigation Methodology Reference

Every investigation follows this exact workflow. Internalize it.

```
1. IDENTIFICATION   → What happened? What systems are involved?
2. PRESERVATION     → Image the disk and memory — never touch the original evidence
3. COLLECTION       → Gather artifacts: logs, registry, browser history, prefetch, LNK files
4. EXAMINATION      → Parse artifacts with tools: Autopsy, Volatility, KAPE, Regripper
5. ANALYSIS         → Connect the dots — build a timeline, identify TTPs
6. REPORTING        → Document findings clearly with evidence, hashes, and MITRE mapping
```

---

## 🔗 Supplemental Resources

- **Volatility 3 Command Reference:** [GitHub Cheatsheet](https://github.com/volatilityfoundation/volatility3/blob/develop/DOCS/v3-cheatsheet.md) — Keep this open during every memory analysis lab.
- **Digital Corpora:** [digitalcorpora.org](https://digitalcorpora.org/) — Free realistic disk images and packet dumps for forensic practice.
- **SANS Windows Forensic Analysis Poster:** [SANS](https://www.sans.org/posters/windows-forensic-analysis/) — Visual map of every registry key, prefetch file, and event log that records user activity.
- **Sandfly Security Blog:** [sandflysecurity.com](https://sandflysecurity.com/blog/) — Linux rootkit and credential theft forensics. Deep technical content.
- **13Cubed YouTube Channel:** [youtube.com/@13Cubed](https://www.youtube.com/@13Cubed) — Best free DFIR video content available. Watch alongside the Volatility and Windows forensics rooms.

---

*[← Phase 3](./03-soc-level-1.md) | [Back to Main Roadmap](../README.md) | [Phase 5 →](./05-projects.md)*
