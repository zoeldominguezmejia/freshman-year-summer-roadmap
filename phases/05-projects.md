# Phase 5 — Forensic Examiner Portfolio Projects
**Timeline: August 13 – August 17 (start) | Continue through sophomore year**
**Hours: ~60 hours total | Projects 1 and 2 before August 18 | Projects 3–5 during sophomore year**

---

## 🎯 Goal
Produce forensic investigation reports that demonstrate examiner-level competency to internship recruiters, forensic firms, and law enforcement agencies. Every project follows professional forensic standards — chain of custody, hash verification, court-ready reporting — because in this profession your documentation is your credibility.

A recruiter reading your GitHub should walk away believing you have done this before.

---

## 📁 Project Overview

| # | Project | Core Skills | Difficulty | Est. Time | When |
|---|---------|-------------|------------|-----------|------|
| 1 | **Insider Threat / IP Theft Investigation** | Windows artifacts, registry, EZ Tools | ⭐⭐ | ~8 hrs | Aug 13–15 |
| 2 | **Ransomware Attack Investigation** | Disk + memory + MITRE mapping | ⭐⭐⭐ | ~12 hrs | Aug 15–17 + first week of semester |
| 3 | **Phishing Campaign Endpoint Forensics** | Email headers, endpoint logs, sandbox | ⭐⭐ | ~10 hrs | Sept–Oct 2026 |
| 4 | **Dead Box Examination — Missing Persons Cold Case** | Full disk exam, timeline, reporting for law enforcement | ⭐⭐⭐ | ~12 hrs | Nov–Dec 2026 |
| 5 | **USB Exfiltration Supertimeline Analysis** | Plaso, anti-forensics detection, litigation report | ⭐⭐⭐⭐ | ~15 hrs | Feb–Mar 2027 |

---

## 🔬 Project 1: Insider Threat / Intellectual Property Theft Investigation
**Folder:** `./project-01-insider-threat/`
**When:** August 13–15

### Scenario
An employee at a technology company was terminated following a performance review. Before returning their equipment, the employee allegedly copied sensitive source code and client contracts to a USB drive and uploaded files to a personal cloud storage account. HR has preserved the workstation disk image under chain of custody and handed it to you. Your report will be reviewed by corporate counsel.

### Why This Project First
You just finished Windows Forensics 1 and 2 and the EZ Tools suite. Every objective below maps directly to what you practiced in Phase 4. Getting a clean, well-documented report done in 2 days before school starts builds the habit and gives you something real on GitHub immediately.

### Objectives
- [ ] Verify evidence integrity — calculate MD5 and SHA-256 hashes of the disk image before touching it; record in your chain of custody documentation
- [ ] Identify all USB devices ever connected using the `USBSTOR` registry key — extract device identifiers, vendor and product IDs, and last connection timestamps using Registry Explorer
- [ ] Parse LNK files with LECmd to recover recently accessed file paths and timestamps
- [ ] Parse Jump Lists with JLECmd to identify applications used and files opened
- [ ] Examine Shellbags with ShellBags Explorer to reconstruct folder navigation history, including folders that no longer exist
- [ ] Parse the MFT with MFTECmd to identify file creation, modification, and access timestamps on files of interest
- [ ] Analyze browser history and downloads folder for evidence of webmail or cloud upload activity (Gmail, Outlook Web, Dropbox, Google Drive, OneDrive)
- [ ] Check for cloud sync application artifacts — Dropbox and OneDrive configuration files and logs
- [ ] Identify any data wiping tool activity — CCleaner runs, Eraser logs, or SDelete usage
- [ ] Build a complete timestamped timeline of suspicious activity in Timeline Explorer
- [ ] Write a litigation-ready forensic investigation report

### Evidence Sources
- **NIST CFReDS:** [cfreds.nist.gov](https://cfreds.nist.gov/) — Start here; officially validated datasets with documented expected findings so you can verify your own work
- **Magnet CTF 2021 image** — Search Magnet Forensics blog for archived CTF images; the 2021 edition has a strong insider threat scenario
- **TryHackMe:** Revisit the Disgruntled room with a full report mindset

### Tools
Registry Explorer, RECmd, LECmd, JLECmd, ShellBags Explorer, MFTECmd, Timeline Explorer (all Eric Zimmerman), Autopsy

### Deliverables
```
project-01-insider-threat/
├── README.md               ← Case summary, scope, tools used, evidence hashes
├── findings.md             ← Full investigation report following the schema below
├── timeline.md             ← Timestamped activity reconstruction
├── usb_analysis.md         ← USB registry findings, device IDs, connection timestamps
├── antiforensics.md        ← Any evidence of wiping or deletion attempts
└── screenshots/            ← Annotated evidence screenshots with timestamps visible
```

---

## 🔬 Project 2: Ransomware Attack Investigation
**Folder:** `./project-02-ransomware/`
**When:** August 15–17, continue into first week of semester if needed

### Scenario
A Windows workstation at a small accounting firm was found encrypted with all user files renamed and a ransom note dropped on the desktop. The IT administrator used FTK Imager to preserve a disk image and a memory dump before rebuilding the system. You are the forensic analyst called in to determine the infection vector, establish an attack timeline, identify the ransomware family, and produce a report suitable for law enforcement referral and cyber insurance filing.

### Why This Project Second
This one adds memory forensics with Volatility on top of the disk skills from Project 1. Doing it second means you already have a report template and documentation rhythm from Project 1, so you can focus your energy on the harder technical work.

### Objectives
- [ ] Verify evidence integrity — hash both the disk image and memory dump; record everything before beginning
- [ ] Analyze the memory dump with Volatility 3 — work through these plugins in order: `windows.pslist`, `windows.pstree`, `windows.cmdline`, `windows.netscan`, `windows.malfind`, `windows.dlllist`
- [ ] Identify the malicious process — look for suspicious parent-child relationships, processes running from unusual paths, and injected memory regions flagged by malfind
- [ ] Examine the disk image in Autopsy — locate the ransomware binary, dropped ransom note, modified file extensions, and any persistence mechanisms (registry Run keys, scheduled tasks, or new services)
- [ ] Use PECmd to check Prefetch for evidence of execution — what ran, when, and how many times
- [ ] Check Windows event logs for lateral movement, new account creation, or privilege escalation artifacts surrounding the infection time
- [ ] Identify the likely initial infection vector
- [ ] Identify the ransomware family — search the ransom note text and file extension on [ID Ransomware](https://id-ransomware.malwarehunterteam.com/) and MalwareBazaar
- [ ] Reconstruct the full attack timeline from initial access through encryption
- [ ] Map the complete attack chain to MITRE ATT&CK with tactic, technique, and sub-technique IDs
- [ ] Write a complete forensic investigation report

### Evidence Sources
- **MemLabs:** [github.com/stuxnet999/MemLabs](https://github.com/stuxnet999/MemLabs) — Free CTF memory dumps; Lab 1 and Lab 3 are the best starting points
- **Digital Corpora:** [digitalcorpora.org](https://digitalcorpora.org/) — Pair a disk image with a MemLabs dump for a combined examination
- **Magnet CTF archives** — Past years have included memory + disk combined scenarios
- **ID Ransomware:** [id-ransomware.malwarehunterteam.com](https://id-ransomware.malwarehunterteam.com/) — Identify ransomware family from note or extension

### Tools
Volatility 3, Autopsy, FTK Imager, PECmd, Registry Explorer, Timeline Explorer, CyberChef, VirusTotal

### Deliverables
```
project-02-ransomware/
├── README.md               ← Case summary, scope, evidence hashes, chain of custody
├── findings.md             ← Full forensic investigation report
├── timeline.md             ← Attack timeline from initial access to encryption
├── memory_analysis.md      ← Volatility findings — process list, network connections, injected regions
├── iocs.md                 ← IPs, domains, file hashes, file names, registry keys
├── mitre_mapping.md        ← Full ATT&CK chain with technique IDs
└── screenshots/            ← Annotated Volatility output, Autopsy findings, Prefetch hits
```

---

## 🔬 Project 3: Phishing Campaign Endpoint Forensics
**Folder:** `./project-03-phishing/`
**When:** September – October 2026

### Scenario
A company's SOC flagged anomalous outbound traffic from an employee workstation. Investigation reveals the user clicked a link in a phishing email four days prior. The endpoint is suspected to be compromised and beaconing to an external C2 server. You have been handed email samples, a browser history export, Windows event logs, and a disk image of the affected workstation.

### Objectives
- [ ] Analyze phishing email headers — document SPF, DKIM, and DMARC failures; identify sender spoofing and originating mail server
- [ ] Extract the malicious URL from browser history and check reputation via URLScan.io and VirusTotal
- [ ] Submit the payload to Any.run — document the process tree, dropped files, C2 connections, DNS queries, and registry modifications made during execution
- [ ] Examine Windows event logs for execution artifacts — Event ID 4688 (process creation with command line), PowerShell ScriptBlock logging (Event ID 4104), and WMI activity
- [ ] Identify persistence mechanisms established by the payload — registry Run keys, scheduled tasks, startup folder, or new services
- [ ] Parse Prefetch with PECmd to corroborate execution timestamps
- [ ] Analyze available PCAP or Zeek logs for C2 beacon patterns — look for regular intervals, unusual user agents, or DNS tunneling
- [ ] Map the full attack to MITRE ATT&CK: T1566.001 → T1059 → T1547 → T1071
- [ ] Write a complete incident response and forensic report

### Evidence Sources
- **PhishTool:** [phishtool.com](https://www.phishtool.com/) — Email header analysis
- **Any.run:** [app.any.run](https://app.any.run/) — Interactive sandbox with full process and network visibility
- **MXToolbox:** [mxtoolbox.com](https://mxtoolbox.com/) — SPF, DKIM, DMARC infrastructure checking
- **CyberDefenders:** Search for phishing or endpoint forensics challenges — several include disk images with phishing compromise scenarios
- **BlueTeamLabs Online:** Has standalone phishing analysis challenges with email samples included

### Tools
PhishTool, Any.run, Autopsy, PECmd, Wireshark or NetworkMiner, CyberChef, VirusTotal, URLScan.io

### Deliverables
```
project-03-phishing/
├── README.md
├── email_analysis.md       ← Header analysis, SPF/DKIM/DMARC findings, spoofed domain documentation
├── endpoint_findings.md    ← Execution artifacts, persistence mechanisms, event log evidence
├── network_analysis.md     ← C2 communication patterns, beacon intervals, DNS findings
├── iocs.md                 ← Full IOC list
├── mitre_mapping.md        ← Complete ATT&CK chain with sub-technique IDs
└── screenshots/
```

---

## 🔬 Project 4: Dead Box Examination — Unidentified Decedent Cold Case
**Folder:** `./project-04-cold-case/`
**When:** November – December 2026

### Scenario
A law enforcement agency has provided a forensic image of a laptop recovered from the residence of an unidentified decedent. The investigation is attempting to establish the identity of the individual, reconstruct their activities in the days before death, and determine whether any third parties were in contact with them. There is no active suspect. Your report will be formatted for submission to the lead detective and must meet evidentiary standards.

### Why This Project
This is the project that most directly reflects what a working digital forensics examiner does for law enforcement. It shifts the objective from "find the attacker" to "reconstruct a person's life from their digital footprint" — which requires a different analytical mindset and a different kind of report. Your Criminal Justice coursework by this point will make this project significantly more meaningful.

### Objectives
- [ ] Verify evidence integrity — full chain of custody documentation from receipt through examination
- [ ] Recover and document user account information — local accounts, Microsoft account linkage, and last login timestamps from the SAM hive and SYSTEM hive
- [ ] Extract browser history, bookmarks, and saved passwords across all installed browsers
- [ ] Examine email client artifacts or webmail browser history for recent communications and contact identities
- [ ] Recover recently accessed documents and files — LNK files, Jump Lists, and Recent Items
- [ ] Examine communication application artifacts — Discord, Telegram, Signal desktop, Skype, or any installed messaging apps
- [ ] Recover deleted files from unallocated space using Autopsy's file carving — focus on images, documents, and communications
- [ ] Extract geolocation data from any recovered images (EXIF metadata) using ExifTool
- [ ] Build a chronological timeline of user activity for the 14 days prior to the recovery date
- [ ] Identify any external accounts, usernames, or aliases that could assist in identification
- [ ] Write a report formatted for law enforcement submission — factual, no speculation, every finding sourced to a specific artifact

### Evidence Sources
- **NIST CFReDS Hacking Case:** [cfreds.nist.gov](https://cfreds.nist.gov/Hacking_Case.html) — One of the most well-known forensic training images; designed for exactly this type of examination
- **Digital Corpora M57-Patents scenario** — Includes multiple disk images from a realistic investigation scenario
- **Magnet CTF 2022 or 2023 archives** — Check the Magnet blog for the most recent publicly available image

### Tools
Autopsy, FTK Imager, Registry Explorer, LECmd, JLECmd, ShellBags Explorer, MFTECmd, ExifTool, Timeline Explorer, Bulk Extractor (for contact and email extraction)

### Deliverables
```
project-04-cold-case/
├── README.md               ← Case intake summary, evidence received, chain of custody log
├── findings.md             ← Full law enforcement formatted report
├── identity_artifacts.md   ← All artifacts relevant to establishing user identity
├── communications.md       ← Reconstructed communications and contact network
├── timeline.md             ← 14-day activity reconstruction
├── recovered_files.md      ← Carved and deleted file recovery documentation
└── screenshots/
```

---

## 🔬 Project 5: USB Exfiltration Supertimeline Analysis with Anti-Forensics Detection
**Folder:** `./project-05-usb-timeline/`
**When:** February – March 2027

### Scenario
A financial firm suspects a data breach. A forensic image of a departing employee's Windows 10 workstation was acquired under chain of custody one hour after their last badge swipe. Your task is to build a complete forensic supertimeline, prove or disprove that data was transferred to external USB storage, identify any deliberate evidence destruction, and produce a report that could support both civil litigation and a potential criminal referral.

### Why This Project Last
Plaso and supertimeline analysis is the most technically demanding skill in this set. By spring semester you will have Security+ done, a semester of CJ courses completed, and four prior projects giving you strong documentation habits. This is the right time to take on the hardest project.

### Objectives
- [ ] Verify evidence integrity — hash the image; record in chain of custody documentation before any processing begins
- [ ] Process the forensic image through Plaso / log2timeline to generate a full supertimeline
- [ ] Filter the supertimeline with psort to isolate USB connection events and surrounding file system activity
- [ ] Extract and cross-correlate all USB artifacts: `USBSTOR` registry key, `setupapi.dev.log`, device interface GUIDs, LNK files created at connection time, and MFT timestamps on files accessed during the connection window
- [ ] Identify specific files that were accessed, copied, or modified during each USB connection event
- [ ] Detect anti-forensics activity — check for VSS deletion (`vssadmin delete shadows`), timestamp manipulation (MACE value anomalies in the MFT), CCleaner or SDelete execution artifacts in Prefetch, and MFT record gaps suggesting file deletion
- [ ] Use MFTECmd to identify MFT sequence number gaps that indicate deleted records
- [ ] Cross-validate findings in Timeline Explorer — filter to the relevant activity window and document the artifact chain
- [ ] Calculate SHA-256 hashes for every artifact cited in the report
- [ ] Write a litigation-ready report that explicitly addresses both what the evidence proves and what it cannot establish

### Evidence Sources
- **NIST CFReDS** — Multiple images suitable for timeline analysis
- **Digital Corpora** — M57 scenario includes timeline-worthy activity across multiple machines
- **Magnet CTF archives** — Most years include Windows 10 images with rich artifact sets

### Tools
Plaso / log2timeline, psort, Timeline Explorer, MFTECmd, Registry Explorer, LECmd, PECmd, Autopsy, Magnet AXIOM (if trial available)

### Deliverables
```
project-05-usb-timeline/
├── README.md               ← Case summary, scope, evidence hashes, chain of custody
├── methodology.md          ← Exact tools, versions, commands run, and collection rationale
├── timeline_export.csv     ← Filtered Plaso output covering the relevant activity window
├── usb_artifacts.md        ← All USB registry, log, and file system findings with timestamps
├── antiforensics.md        ← Evidence of deliberate destruction attempts and their significance
├── findings.md             ← Complete narrative findings with confidence levels stated explicitly
└── screenshots/
```

---

## 📋 Forensic Investigation Report Schema

Every report follows this structure. Do not deviate from it.

```markdown
# Forensic Investigation Report
**Case Number:** [sequential — e.g. FE-2026-001]
**Examiner:** [your name]
**Date of Report:** [date]
**Classification:** Confidential

---

## 1. Executive Summary
2–3 sentences maximum. What happened, what was found, what is the conclusion.
Written for a non-technical reader — attorney, HR director, detective, or judge.

## 2. Scope & Objectives
What system or evidence was examined. The specific questions this examination
was tasked to answer. What is explicitly outside the scope of this examination.

## 3. Evidence Received
| Item | Description | MD5 Hash | SHA-256 Hash | Date Received |
|------|-------------|----------|--------------|---------------|
| E001 | [filename] | [hash] | [hash] | [date] |
All hashes verified before examination began.
All examination performed on forensic copies only. Originals not modified.

## 4. Methodology
Tools used (name and exact version). Acquisition method. Examination approach.
Detailed enough that another qualified examiner could reproduce every step.

## 5. Findings
Detailed, factual, and chronological. No speculation. No opinion.
Every claim is supported by a specific artifact, file path, registry key,
or log entry with a timestamp. Cite your evidence like you are writing
for someone who will fact-check every sentence in court.

## 6. Timeline of Events
| Timestamp (UTC) | Event | Artifact Source | Confidence |
|-----------------|-------|-----------------|------------|

## 7. Indicators of Compromise
| Type | Value | First Seen | Source Artifact |
|------|-------|------------|-----------------|
| File Hash | SHA-256: ... | [timestamp] | [path] |
| IP Address | x.x.x.x | [timestamp] | [artifact] |
| Domain | evil.com | [timestamp] | [artifact] |

## 8. MITRE ATT&CK Mapping
| Tactic | Technique | Sub-Technique | ID | Observed Evidence |
|--------|-----------|---------------|----|-------------------|
(Include for incident response and malware cases. Omit for cold case and civil matters.)

## 9. Conclusions
What the evidence shows. Distinguish explicitly between what is proven by
artifact evidence and what is inferred. State your confidence level.
Never overstate what the evidence establishes.

## 10. Recommendations
What the organization or agency should do based on the findings.

## 11. Examiner Certification
I, [name], certify that the findings in this report accurately represent
the results of my forensic examination to the best of my knowledge and ability,
and that all examination was performed on forensically verified copies of the
original evidence. No original evidence was modified during this examination.

Signed: _________________ Date: _________________
```

---

## 🌐 Practice Platforms

| Platform | Free? | Best For |
|----------|-------|----------|
| [CyberDefenders](https://cyberdefenders.org/) | ✅ Free | Forensics CTFs — do one per week during the semester |
| [BlueTeamLabs Online](https://blueteamlabs.online/) | ✅ Free tier | SOC and forensics scenarios |
| [MemLabs](https://github.com/stuxnet999/MemLabs) | ✅ Free | Memory forensics CTF challenges |
| [NIST CFReDS](https://cfreds.nist.gov/) | ✅ Free | Validated forensic datasets with known correct answers |
| [Digital Corpora](https://digitalcorpora.org/) | ✅ Free | Realistic disk images and memory dumps |
| [Magnet CTF Archives](https://www.magnetforensics.com/blog/) | ✅ Free | Annual forensic CTF — closest thing to real casework |
| [HackTheBox Forensics](https://app.hackthebox.com/challenges) | ✅ Free tier | Harder challenges once the others feel comfortable |

---

## 🏆 Milestones

### Before August 18 (semester begins)
- [ ] Project 1 (Insider Threat) — full report written and pushed to GitHub
- [ ] Project 2 (Ransomware) — in progress; complete by end of first week of semester if needed
- [ ] GitHub repository has clean structure and professional README files
- [ ] LinkedIn updated with all earned certs, skills, and GitHub link

### Fall 2026
- [ ] Project 2 fully complete if not done over summer
- [ ] Project 3 (Phishing Endpoint Forensics) — complete by late October
- [ ] Project 4 (Cold Case) — complete by mid-December before finals

### Spring 2027
- [ ] Project 5 (USB Supertimeline) — complete by mid-March
- [ ] All five reports live on GitHub with clean writeups
- [ ] Internship or externship applications submitted

---

*[← Phase 4](./04-dfir-deep-dive.md) | [Back to Main Roadmap](../README.md)*
