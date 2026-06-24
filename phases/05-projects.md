# Phase 5 — Forensic Examiner Portfolio
**August 2026 – April 2027 | 6 Projects | Public Documentation**

---

## Overview

This phase is the portfolio. Every project here is publicly documented so other students, junior examiners, and hiring managers can see exactly how each investigation was approached — not just the conclusions, but the methodology, the tools, the artifact sources, and the reasoning at each step.

Projects are ordered by when they're built, but they're designed to be useful to anyone who finds them. If you're a student working through a forensics course and looking for a real example of how to document an investigation, these are written for you.

---

## Project Index

| # | Project | Type | When |
|---|---------|------|------|
| 1 | [Corporate Breach Investigation — Full Case](#project-1-corporate-breach-investigation) | Combined IR + Forensic Case | July–Aug 2026 |
| 2 | [NIST Hacking Case — Complete Public Analysis](#project-2-nist-hacking-case) | Community Reference Document | Sept–Oct 2026 |
| 3 | [Anti-Forensics Detection Study](#project-3-anti-forensics-detection-study) | Technical Research | Nov–Dec 2026 |
| 4 | [Browser Artifact Parser](#project-4-browser-artifact-parser) | Open Source Tool | Jan–Feb 2027 |
| 5 | [KAPE Target Contribution](#project-5-kape-target-contribution) | Open Source Contribution | Mar–Apr 2027 |

---

## Project 1: Corporate Breach Investigation — Full Case
**Folder:** `./project-01-corporate-breach/`
**When:** Mid-July through August 13, 2026

### What This Is

A full corporate breach investigation conducted against publicly available forensic images. The investigation covers the complete attack chain from initial access through exfiltration — combining memory forensics, disk forensics, Windows artifact analysis, and network traffic analysis into a single unified case.

This is not two separate projects. It is one investigation with two phases: the external breach (ransomware or malware delivery from outside) and the insider component (data exfiltration from within). In practice, these often occur together — an attacker gains initial access, moves laterally, and exfiltrates data before deploying ransomware. Treating them as one case produces a more realistic and more useful portfolio piece than two disconnected reports.

### Why This Structure

Most beginner forensics portfolios contain isolated exercises — "here is my Volatility output" or "here is my Autopsy screenshot." This project is structured the way a real engagement would be: a case number, a scope, documented evidence with verified hashes, a methodology log, a timeline, MITRE ATT&CK mapping, and a final report written for a non-technical reader.

If a recruiter at Kroll, Deloitte, or FTI looks at this project, the question they are asking is not "did you run the right commands." It is "does this person know how to document an investigation to a professional standard." That is what this project is designed to demonstrate.

### Investigation Phases

**Phase A — External Compromise**

A Windows workstation at a small accounting firm was found encrypted. The IT administrator preserved a disk image and memory dump before rebuilding the system.

Objectives:
- [ ] Verify evidence integrity — calculate MD5 and SHA-256 hashes of the disk image and memory dump; record in chain of custody documentation
- [ ] Analyze the memory dump with Volatility 3: `windows.pslist`, `windows.pstree`, `windows.cmdline`, `windows.netscan`, `windows.malfind`, `windows.dlllist`
- [ ] Identify the malicious process — suspicious parent-child relationships, processes in unusual paths, injected memory regions
- [ ] Examine the disk image in Autopsy — ransomware binary, ransom note, modified file extensions, persistence mechanisms (Run keys, scheduled tasks, services)
- [ ] Check Prefetch with PECmd — what executed, when, and how many times
- [ ] Parse Windows Event Logs — privilege escalation, new account creation, lateral movement
- [ ] Identify the initial infection vector
- [ ] Identify the ransomware family using ID Ransomware
- [ ] Map the full attack chain to MITRE ATT&CK

**Phase B — Insider Exfiltration**

Evidence suggests an employee was also exfiltrating data in the weeks before the external compromise. The same disk image is examined for insider threat artifacts.

Objectives:
- [ ] Identify USB devices connected using the USBSTOR registry key — extract device identifiers, vendor IDs, and last connection timestamps with Registry Explorer
- [ ] Parse LNK files with LECmd — recently accessed file paths and timestamps
- [ ] Parse Jump Lists with JLECmd — applications used and files opened
- [ ] Examine Shellbags with ShellBags Explorer — folder navigation history including deleted folders
- [ ] Parse the MFT with MFTECmd — file creation, modification, and access timestamps on files of interest
- [ ] Analyze browser history and downloads for webmail and cloud upload activity
- [ ] Check for cloud sync application artifacts
- [ ] Check Prefetch for evidence of data wiping tools (CCleaner, SDelete, Eraser)
- [ ] Build a unified timestamped timeline in Timeline Explorer

**Combined Deliverables**
```
project-01-corporate-breach/
├── README.md                  ← Case overview, scope, evidence hashes, tools used
├── chain_of_custody.md        ← Evidence log with MD5 + SHA-256 hashes
├── methodology.md             ← Every tool, version, command, and decision documented
├── phase-a-external/
│   ├── memory_analysis.md     ← Volatility findings with annotated output
│   ├── disk_analysis.md       ← Autopsy findings
│   ├── iocs.md                ← IPs, hashes, file names, registry keys
│   └── mitre_mapping.md       ← ATT&CK chain with technique IDs
├── phase-b-insider/
│   ├── usb_analysis.md        ← USBSTOR findings
│   ├── file_activity.md       ← LNK, Jump Lists, Shellbags, MFT findings
│   ├── browser_analysis.md    ← Browser history and download artifacts
│   └── antiforensics.md       ← Evidence of wiping or deletion attempts
├── timeline.md                ← Unified attack + exfiltration timeline (UTC)
├── final_report.md            ← Complete forensic investigation report (see schema)
└── screenshots/               ← Annotated evidence screenshots
```

### Evidence Sources
- [MemLabs](https://github.com/stuxnet999/MemLabs) — free CTF memory dumps; Lab 1 and Lab 3 recommended
- [Digital Corpora](https://digitalcorpora.org/) — free forensic disk images
- [NIST CFReDS](https://cfreds.nist.gov/) — validated datasets with documented expected findings
- [ID Ransomware](https://id-ransomware.malwarehunterteam.com/) — identify ransomware family from note or file extension
- [Magnet CTF Archives](https://www.magnetforensics.com/blog/) — annual forensic CTF images

### Tools
Volatility 3 · Autopsy · FTK Imager · KAPE · PECmd · Registry Explorer · RECmd · LECmd · JLECmd · ShellBags Explorer · MFTECmd · Timeline Explorer · CyberChef · VirusTotal

---

## Project 2: NIST Hacking Case — Complete Public Analysis
**Folder:** `./project-02-nist-hacking-case/`
**When:** September – October 2026

### What This Is

The NIST Hacking Case is one of the most widely assigned forensic training images in university courses and professional certification preparation. Despite this, there is almost no freely available example of a complete, professionally formatted forensic examination report based on it.

This project fills that gap. The goal is to produce a public document that a student working through this image in a university course can use as a reference for what a complete examination looks like — not just which artifacts to find, but how to document them to professional standards.

### The Image
**NIST CFReDS Hacking Case:** [cfreds.nist.gov/Hacking_Case.html](https://cfreds.nist.gov/Hacking_Case.html)

Publicly available, with a documented scenario and published expected findings. You can verify your own work against the official answers, which makes it ideal for building documentation discipline.

### Objectives
- [ ] Download and verify image integrity against published hash values
- [ ] Document complete examination environment (OS, tool versions, VM configuration)
- [ ] Conduct full disk examination in Autopsy — systematic pass through every artifact category
- [ ] Parse all relevant Windows artifacts using EZ Tools
- [ ] Reconstruct browser history and email artifacts
- [ ] Build a complete activity timeline in Timeline Explorer and export it
- [ ] Answer every question in the official NIST scenario documentation
- [ ] Write a complete forensic examination report — every finding sourced to a specific artifact with file path, hash, and timestamp
- [ ] Write a companion methodology document — every tool, version, command, and decision
- [ ] Publish with a clear README explaining what the repository is and who it is for

### What Makes This Different

After each major finding section, include a brief examiner note: *why* is this artifact significant? *What* does it tell you that other artifacts don't? The report is written to be a teaching resource, not just a case record. That framing makes it genuinely useful to other students and positions it as a community contribution rather than just a homework assignment.

### Deliverables
```
project-02-nist-hacking-case/
├── README.md               ← What this repo is, who it's for, how to use it
├── examination_report.md   ← Full professional forensic report
├── methodology.md          ← Every tool, version, command, and decision documented
├── timeline_export.csv     ← Full Timeline Explorer output
├── artifact_notes.md       ← Examiner notes on the significance of each artifact type
├── case_questions.md       ← NIST case questions with documented answers and evidence citations
└── screenshots/            ← Annotated screenshots of every significant finding
```

---

## Project 3: Anti-Forensics Detection Study
**Folder:** `./project-03-antiforensics/`
**When:** November – December 2026

### What This Is

A controlled research study documenting exactly what forensic traces common anti-forensics techniques leave behind — from the examiner's perspective, not the attacker's.

There is substantial public documentation on how anti-forensics tools work. There is very little on what artifacts those tools leave behind for an examiner to detect. This study is designed to be that resource.

### Setup
- Windows 10 VM with clean baseline snapshot before each test
- FTK Imager for before-and-after imaging
- Full EZ Tools suite, Autopsy, and Volatility for examination
- Full methodology documented for reproducibility

### Techniques Studied

**Technique 1: Timestamp Manipulation (Timestomp)**
Modify MACE timestamps on a set of files. Document which timestamp fields change, which don't, what MFT inconsistencies reveal the manipulation, and what a natural timestamp pattern looks like by comparison.

**Technique 2: Secure File Deletion (SDelete)**
Delete files with SDelete. Document what Prefetch reveals about SDelete execution, what MFT record gaps indicate, what can and cannot be recovered, and what an examiner can prove even when file content is unrecoverable.

**Technique 3: Volume Shadow Copy Deletion**
Delete VSS snapshots with `vssadmin delete shadows /all`. Document Event IDs that record the deletion (Event 524 / ID 1102 equivalent), what registry artifacts remain, and how an examiner establishes that VSS copies were deliberately destroyed.

**Technique 4: Event Log Clearing**
Clear Windows Security, System, and Application event logs. Document Event ID 1102 (Security log cleared) and 104 (System log cleared), timing artifacts, and what partial log data survives.

**Technique 5: CCleaner Execution**
Run CCleaner aggressively against a system with known activity. Document what it removes, what it does not remove, what Prefetch and registry artifacts reveal about its execution, and what evidence survives.

### Document Structure for Each Technique
```
## [Technique Name]
### What It Does
### How It Was Performed (exact commands and settings)
### Before State (artifacts present pre-execution)
### After State (artifacts present post-execution)
### What the Examiner Can Detect
### What Cannot Be Recovered
### Detection Tools and Methods
### Examiner Guidance
```

### Deliverables
```
project-03-antiforensics/
├── README.md
├── methodology.md              ← VM setup, tool versions, steps for each technique
├── technique-01-timestomp.md
├── technique-02-sdelete.md
├── technique-03-vss-deletion.md
├── technique-04-log-clearing.md
├── technique-05-ccleaner.md
├── summary.md                  ← Cross-technique findings, detection recommendations
└── screenshots/                ← Before and after screenshots with annotations
```

---

## Project 4: Browser Artifact Parser
**Folder:** `./project-04-browser-parser/`
**When:** January – February 2027

### What This Is

A Python command-line tool that parses forensic artifacts from Chrome, Firefox, Edge, and Brave and outputs a unified, examiner-ready CSV timeline compatible with Timeline Explorer.

Every major browser stores history, downloads, cookies, and form autofill in SQLite databases — but the schema differs between browsers and versions. Commercial tools like Magnet AXIOM handle this well but cost thousands of dollars. Open source alternatives are fragmented and inconsistently maintained. This tool is designed to be a free, well-documented alternative for students, small forensic firms, and law enforcement agencies without commercial tool budgets.

### Core Features
- Parse Chrome, Firefox, Edge, and Brave SQLite databases from a provided evidence path
- Extract history, downloads, searches, cookies (metadata only — no content), and form autofill
- Normalize timestamps across browsers to UTC
- Output unified CSV compatible with Timeline Explorer
- Calculate SHA-256 hash of each source database file for chain of custody
- Generate plain text summary report alongside CSV
- Handle locked or corrupted databases gracefully with clear error messages
- `--browser` flag to target a specific browser or parse all detected

### Usage
```bash
python browserparse.py --evidence /path/to/user/profile --output ./results
python browserparse.py --evidence /path/to/user/profile --browser chrome --output ./results
```

### Output Structure
```
results/
├── browser_timeline.csv        ← Unified timeline, all browsers, all artifact types
├── chrome_history.csv
├── firefox_history.csv
├── edge_history.csv
├── brave_history.csv
├── summary_report.txt          ← Artifact counts and source file hash values
└── evidence_hashes.txt         ← SHA-256 hashes of all source database files
```

### Development Approach
Start with Chrome history only. Get that working cleanly and outputting correct UTC timestamps before adding other browsers. Then Firefox. Then Edge and Brave. Then additional artifact types. Commit working versions at each stage so the GitHub history shows the development process — this is itself useful to other developers building on the work.

### Deliverables
```
project-04-browser-parser/
├── README.md               ← What the tool does, installation, usage, output format
├── browserparse.py
├── parsers/
│   ├── chrome.py
│   ├── firefox.py
│   ├── edge.py
│   └── brave.py
├── requirements.txt
├── tests/                  ← Test cases with sample database files
├── CONTRIBUTING.md
└── LICENSE                 ← MIT
```

---

## Project 5: KAPE Target Contribution
**Folder:** `./project-05-kape-target/`
**When:** March – April 2027

### What This Is

Research a specific application or artifact category not yet covered by an existing KAPE Target, document every forensic artifact that application leaves on a Windows system, write a properly formatted KAPE Target YAML file, and submit it as a pull request to the official KapeFiles repository.

This is not a project that lives only on your GitHub. If the Target is accepted, your name goes into the contributor list of a tool that practicing examiners use in real casework every day.

### How to Find a Gap

Browse the existing Targets at [github.com/EricZimmerman/KapeFiles](https://github.com/EricZimmerman/KapeFiles). Good candidates are applications not yet covered that appear regularly in forensic cases: newer communication platforms, cloud storage clients, developer tools, or social and gaming applications increasingly encountered in criminal investigations.

### Objectives
- [ ] Identify a genuine gap in the KapeFiles Targets repository
- [ ] Install the target application in a clean Windows 10 VM
- [ ] Use the application normally for several days to generate realistic artifacts
- [ ] Document every artifact — files created, registry keys written, databases used, prefetch entries generated, network connections made
- [ ] Write the KAPE Target YAML file following official formatting standards
- [ ] Test the Target against your VM image to verify it collects what you documented
- [ ] Write a companion document explaining each artifact's forensic significance
- [ ] Submit a pull request to the official KapeFiles repository
- [ ] Respond to reviewer feedback and iterate until accepted

### Example Target Structure
```yaml
Name: ApplicationName
Description: Collects artifacts related to ApplicationName
Author: Your Name
Version: 1.0
Id: [GUID]
RecreateDirectories: true
Targets:
    -
        Name: ApplicationName Database
        Category: ApplicationName
        Path: C:\Users\%user%\AppData\Roaming\ApplicationName\
        FileMask: '*.db'
        Recursive: true
        IsDirectory: false
```

### Deliverables
```
project-05-kape-target/
├── README.md               ← Application targeted, why it matters, artifact summary
├── artifact_research.md    ← Every artifact found with forensic significance
├── ApplicationName.tkape   ← The KAPE Target file
├── methodology.md          ← VM setup, examination approach, testing process
└── screenshots/            ← Artifact locations and Target testing results
```

The pull request to KapeFiles is the real deliverable. Everything in this folder is the research documentation that supports it.

---

## Forensic Investigation Report Schema

All investigation reports follow this structure. Consistent formatting across every project makes the portfolio readable as a whole, not just as individual projects.

```markdown
# Forensic Investigation Report
**Case Number:** [e.g. FE-2026-001]
**Examiner:** [name]
**Date of Report:** [date]
**Classification:** Confidential

---

## 1. Executive Summary
2–3 sentences. What happened, what was found, what is the conclusion.
Written for a non-technical reader: attorney, HR director, detective, or judge.

## 2. Scope & Objectives
What system or evidence was examined. What specific questions this examination
was tasked to answer. What is explicitly outside scope.

## 3. Evidence Received
| Item | Description | MD5 | SHA-256 | Date Received |
|------|-------------|-----|---------|---------------|
| E001 | [filename]  | [hash] | [hash] | [date] |

All hashes verified before examination began.
All examination performed on forensic copies only. Originals not modified.

## 4. Methodology
Tools used (name and exact version). Acquisition method. Examination approach.
Detailed enough that another qualified examiner could reproduce every step.

## 5. Findings
Detailed, factual, chronological. No speculation. No opinion.
Every claim supported by a specific artifact with file path, hash, and timestamp.

## 6. Timeline of Events
| Timestamp (UTC) | Event | Artifact Source | Confidence |
|-----------------|-------|-----------------|------------|

## 7. Indicators of Compromise
| Type | Value | First Seen | Source Artifact |
|------|-------|------------|-----------------|
(Include for IR and malware cases.)

## 8. MITRE ATT&CK Mapping
| Tactic | Technique | Sub-Technique | ID | Observed Evidence |
|--------|-----------|---------------|----|-------------------|
(Include for IR and malware cases. Omit for civil matters.)

## 9. Conclusions
What the evidence shows. Explicitly distinguish between what is proven by
artifact evidence and what is inferred. State confidence level.
Never overstate what the evidence establishes.

## 10. Recommendations
What the organization or agency should do based on the findings.

## 11. Examiner Certification
I, [name], certify that the findings in this report accurately represent
the results of my forensic examination to the best of my knowledge and
ability, and that all examination was performed on forensically verified
copies of the original evidence. No original evidence was modified
during this examination.

Signed: _________________ Date: _________________
```

---

## Practice Platforms

| Platform | Free? | Best For |
|----------|-------|----------|
| [CyberDefenders](https://cyberdefenders.org/) | ✅ | Forensics CTFs — one per week during semester |
| [BlueTeamLabs Online](https://blueteamlabs.online/) | ✅ tier | SOC and forensics scenarios |
| [MemLabs](https://github.com/stuxnet999/MemLabs) | ✅ | Memory forensics CTF challenges |
| [NIST CFReDS](https://cfreds.nist.gov/) | ✅ | Validated datasets with documented correct answers |
| [Digital Corpora](https://digitalcorpora.org/) | ✅ | Realistic disk images and memory dumps |
| [Magnet CTF Archives](https://www.magnetforensics.com/blog/) | ✅ | Annual forensic CTF — closest to real casework |
| [HackTheBox Forensics](https://app.hackthebox.com/challenges) | ✅ tier | Harder challenges |

---

## Milestones

**Summer 2026 (by Aug 13)**
- [ ] Project 1 complete — full report pushed to GitHub
- [ ] GitHub repo has clean structure and professional README on every folder
- [ ] LinkedIn updated with DFIR skills and GitHub link

**Fall 2026**
- [ ] Project 2 (NIST Hacking Case) — complete by late October
- [ ] Project 3 (Anti-Forensics Study) — complete by mid-December

**Spring 2027**
- [ ] Project 4 (Browser Parser) — working tool published by mid-February
- [ ] Project 5 (KAPE Target) — pull request submitted by April
- [ ] All five projects live on GitHub with clean documentation

---

*[← Phase 4](./04-dfir-deep-dive.md) | [Back to Roadmap](../README.md)*
