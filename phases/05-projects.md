# Phase 5 — Forensic Examiner Portfolio Projects
**Timeline: August 13 – August 17 (start) | Continue through sophomore year**
**Hours: ~80 hours total | Projects 1 and 2 before August 18 | Projects 3–6 during sophomore year**

---

## 🎯 Goal
Build a portfolio that does two things simultaneously: demonstrates your competency as a forensic examiner to internship recruiters and hiring managers, and contributes something genuinely useful to the digital forensics community. Every project here either produces a tool, a resource, or a contribution that other examiners and students can actually use — not just another CTF writeup sitting on GitHub.

---

## 📁 Project Overview

| # | Project | Type | Difficulty | Est. Time | When |
|---|---------|------|------------|-----------|------|
| 1 | **Insider Threat Investigation** | Foundational case report | ⭐⭐ | ~8 hrs | Aug 13–15 |
| 2 | **Ransomware Attack Investigation** | Foundational case report | ⭐⭐⭐ | ~12 hrs | Aug 15–17 + first week of semester |
| 3 | **NIST Hacking Case — Full Public Analysis** | Community reference document | ⭐⭐⭐ | ~15 hrs | Sept–Oct 2026 |
| 4 | **Anti-Forensics Detection Study** | Technical research + community resource | ⭐⭐⭐ | ~15 hrs | Nov–Dec 2026 |
| 5 | **Browser Artifact Parser** | Open source tool | ⭐⭐⭐⭐ | ~20 hrs | Jan–Feb 2027 |
| 6 | **KAPE Target Contribution** | Direct open source contribution | ⭐⭐⭐ | ~10 hrs | Mar–Apr 2027 |

---

## 🔬 Project 1: Insider Threat Investigation
**Folder:** `./project-01-insider-threat/`
**When:** August 13–15

### Scenario
An employee at a technology company was terminated following a performance review. Before returning their equipment, the employee allegedly copied sensitive source code and client contracts to a USB drive and uploaded files to personal cloud storage. HR has preserved the workstation disk image under chain of custody. Your report will be reviewed by corporate counsel.

### Why This Project First
You just finished Windows Forensics 1 and 2 and the full EZ Tools suite in Phase 4. Every objective here maps directly to what you just practiced. The goal is to get a clean, professionally documented report finished in two days before school starts — building the documentation habit and giving you something real on GitHub immediately.

### Objectives
- [ ] Verify evidence integrity — calculate MD5 and SHA-256 hashes of the disk image before touching it; record in chain of custody documentation
- [ ] Identify all USB devices ever connected using the `USBSTOR` registry key — extract device identifiers, vendor and product IDs, and last connection timestamps using Registry Explorer
- [ ] Parse LNK files with LECmd to recover recently accessed file paths and timestamps
- [ ] Parse Jump Lists with JLECmd to identify applications used and files opened
- [ ] Examine Shellbags with ShellBags Explorer to reconstruct folder navigation history including folders that no longer exist
- [ ] Parse the MFT with MFTECmd to identify file creation, modification, and access timestamps on files of interest
- [ ] Analyze browser history and downloads for webmail or cloud upload activity — Gmail, Outlook Web, Dropbox, Google Drive, OneDrive
- [ ] Check for cloud sync application artifacts — configuration files and logs
- [ ] Identify any data wiping tool activity — CCleaner runs, Eraser logs, or SDelete usage in Prefetch
- [ ] Build a complete timestamped timeline in Timeline Explorer
- [ ] Write a litigation-ready forensic investigation report using the schema at the bottom of this document

### Evidence Sources
- **NIST CFReDS:** [cfreds.nist.gov](https://cfreds.nist.gov/) — Start here; officially validated datasets with documented expected findings so you can verify your own work
- **Magnet CTF 2021 archive:** Search the Magnet Forensics blog — the 2021 edition has a strong insider threat scenario
- **TryHackMe:** Revisit the Disgruntled room with a full report mindset if you need a simpler starting image

### Tools
Registry Explorer, RECmd, LECmd, JLECmd, ShellBags Explorer, MFTECmd, PECmd, Timeline Explorer, Autopsy

### Deliverables
```
project-01-insider-threat/
├── README.md               ← Case summary, scope, tools used, evidence hashes
├── findings.md             ← Full investigation report
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
A Windows workstation at a small accounting firm was found encrypted with all user files renamed and a ransom note on the desktop. The IT administrator preserved a disk image and memory dump with FTK Imager before rebuilding the system. You are the forensic analyst called in to determine the infection vector, establish a timeline, identify the ransomware family, and produce a report suitable for law enforcement referral and cyber insurance filing.

### Why This Project Second
This adds memory forensics with Volatility on top of the disk skills from Project 1. Doing it second means you already have a report template and documentation rhythm, so you can focus your energy on the harder technical work rather than figuring out how to structure a report at the same time.

### Objectives
- [ ] Verify evidence integrity — hash both the disk image and memory dump before beginning
- [ ] Analyze the memory dump with Volatility 3 — work through these plugins in order: `windows.pslist`, `windows.pstree`, `windows.cmdline`, `windows.netscan`, `windows.malfind`, `windows.dlllist`
- [ ] Identify the malicious process — look for suspicious parent-child relationships, processes running from unusual paths, and injected memory regions flagged by malfind
- [ ] Examine the disk image in Autopsy — locate the ransomware binary, ransom note, modified file extensions, and persistence mechanisms including registry Run keys, scheduled tasks, and new services
- [ ] Use PECmd to check Prefetch for execution evidence — what ran, when, and how many times
- [ ] Check Windows event logs for privilege escalation, new account creation, or lateral movement artifacts surrounding the infection window
- [ ] Identify the likely initial infection vector
- [ ] Identify the ransomware family using the ransom note text and encrypted file extension on ID Ransomware
- [ ] Reconstruct the full attack timeline from initial access through encryption
- [ ] Map the complete attack chain to MITRE ATT&CK with tactic, technique, and sub-technique IDs
- [ ] Write a complete forensic investigation report

### Evidence Sources
- **MemLabs:** [github.com/stuxnet999/MemLabs](https://github.com/stuxnet999/MemLabs) — Lab 1 and Lab 3 are the best starting points for memory analysis practice
- **Digital Corpora:** [digitalcorpora.org](https://digitalcorpora.org/) — Pair a disk image here with a MemLabs memory dump for a combined examination
- **ID Ransomware:** [id-ransomware.malwarehunterteam.com](https://id-ransomware.malwarehunterteam.com/) — Identify ransomware family from note text or file extension

### Tools
Volatility 3, Autopsy, FTK Imager, PECmd, Registry Explorer, Timeline Explorer, CyberChef, VirusTotal

### Deliverables
```
project-02-ransomware/
├── README.md               ← Case summary, scope, evidence hashes, chain of custody
├── findings.md             ← Full forensic investigation report
├── timeline.md             ← Attack timeline from initial access to encryption
├── memory_analysis.md      ← Volatility findings — processes, network connections, injected regions
├── iocs.md                 ← IPs, domains, file hashes, file names, registry keys
├── mitre_mapping.md        ← Full ATT&CK chain with technique IDs
└── screenshots/            ← Annotated Volatility output, Autopsy findings, Prefetch hits
```

---

## 🔬 Project 3: NIST Hacking Case — Full Public Analysis
**Folder:** `./project-03-nist-hacking-case/`
**When:** September – October 2026
**Type: Community Reference Document**

### What This Is
The NIST Hacking Case is one of the most well-known forensic training images in existence — it has been used in university courses and certification training for years. Despite this, there is almost no freely available example of a complete, professionally formatted forensic examination report based on it that a student or junior examiner could actually reference. You are going to write that document and publish it publicly.

### Why This Matters to the Community
Good public examples of professional forensic reports are genuinely rare. Forensics professors assign the NIST Hacking Case regularly but students have no reference point for what a complete examination should look like. A thorough, well-documented public analysis with full methodology, every artifact sourced, every tool command recorded, and findings written to professional standards would be cited, shared, and used by students and educators. This is a resource gap you can actually fill.

### The Image
**NIST CFReDS Hacking Case:** [cfreds.nist.gov/Hacking_Case.html](https://cfreds.nist.gov/Hacking_Case.html)

This is a publicly available forensic image with a documented scenario and known expected findings — meaning you can verify your own work against the official answers. It involves a suspected hacking incident on a Windows system and covers file system artifacts, browser history, email artifacts, and user activity reconstruction.

### Objectives
- [ ] Download the image and verify integrity against the published hash values before beginning
- [ ] Document your complete examination environment — OS, tool versions, VM configuration
- [ ] Conduct a full disk forensic examination using Autopsy — work systematically through every artifact category
- [ ] Parse and document all relevant Windows artifacts using EZ Tools — LNK files, Jump Lists, Shellbags, Prefetch, MFT, registry hives
- [ ] Reconstruct browser history and any email artifacts present
- [ ] Build a complete user activity timeline in Timeline Explorer and export it
- [ ] Answer every question posed in the official NIST case scenario documentation
- [ ] Write a complete forensic examination report following professional standards — every finding sourced to a specific artifact with file path, hash, and timestamp
- [ ] Write a companion methodology document explaining every tool used, every command run, and every decision made during the examination
- [ ] Publish everything to GitHub with a clear README explaining what the repository is and who it is for

### What Makes This Different From a Normal Project
The report is written to be a teaching resource, not just a case record. After each major finding section, include a brief examiner note explaining *why* that artifact is significant and *what* it tells an examiner that other artifacts do not. You are writing for the student who will find this repository six months from now trying to figure out how to approach the same image.

### Deliverables
```
project-03-nist-hacking-case/
├── README.md               ← What this repo is, who it's for, how to use it
├── examination_report.md   ← Full professional forensic report
├── methodology.md          ← Every tool, version, command, and decision documented
├── timeline_export.csv     ← Full Timeline Explorer output
├── artifact_notes.md       ← Examiner notes explaining the significance of each artifact type found
├── case_questions.md       ← Official NIST case questions with your documented answers and evidence citations
└── screenshots/            ← Annotated screenshots of every significant finding
```

---

## 🔬 Project 4: Anti-Forensics Detection Study
**Folder:** `./project-04-antiforensics/`
**When:** November – December 2026
**Type: Technical Research + Community Resource**

### What This Is
A controlled research study where you deliberately perform common anti-forensics techniques on a Windows VM, image the system before and after each technique, and document exactly what forensic traces each technique leaves behind from the examiner's perspective — and what tools and methods can detect them.

### Why This Matters to the Community
There is substantial public documentation on how anti-forensics tools work from an attacker's perspective. There is very little freely available documentation on exactly what artifacts those same tools leave behind from the examiner's perspective. Security researchers publish malware analyses but the examiner's view of anti-forensics detection is underrepresented in public literature. This research would be genuinely citable by other students, junior examiners, and educators.

### Setup
- Windows 10 VM (clean baseline snapshot before each test)
- FTK Imager for before and after imaging
- Full EZ Tools suite, Autopsy, and Volatility for examination
- Document every step of the setup so the methodology is fully reproducible

### Anti-Forensics Techniques to Study

**Technique 1: Timestamp Manipulation with Timestomp**
- Modify MACE (Modified, Accessed, Created, Entry Modified) timestamps on a set of files
- Image the VM and examine the MFT with MFTECmd
- Document: what timestamp fields were changed, which were not, what inconsistencies in the MFT reveal the manipulation, and what a natural timestamp pattern looks like by comparison

**Technique 2: Secure File Deletion with SDelete**
- Create a set of files, then delete them with SDelete (Sysinternals)
- Image the VM and attempt recovery with Autopsy file carving and MFT analysis
- Document: what Prefetch reveals about SDelete execution, what MFT record gaps indicate, what can and cannot be recovered, and what the examiner can prove even when file content is unrecoverable

**Technique 3: Volume Shadow Copy Deletion**
- Create VSS snapshots, then delete them with `vssadmin delete shadows /all`
- Image the VM and examine Windows event logs and registry artifacts
- Document: which event IDs record VSS deletion, what registry artifacts remain, and how an examiner establishes that VSS copies were deliberately destroyed

**Technique 4: Log Clearing**
- Clear Windows Security, System, and Application event logs
- Image the VM and examine what artifacts the clearing action itself left behind
- Document: Event ID 1102 (Security log cleared) and 104 (System log cleared), what the examiner can establish about the clearing action and its timing, and what partial log data may survive

**Technique 5: CCleaner Execution**
- Run CCleaner with aggressive settings against a system with known browser history and recent file activity
- Image before and after
- Document: what CCleaner removes, what it does not remove, what Prefetch and registry artifacts reveal about CCleaner execution, and what evidence survives a CCleaner run

### Deliverables
```
project-04-antiforensics/
├── README.md               ← What this study is, methodology overview, how to reproduce it
├── methodology.md          ← Full VM setup, tool versions, exact steps for each technique
├── technique-01-timestomp.md
├── technique-02-sdelete.md
├── technique-03-vss-deletion.md
├── technique-04-log-clearing.md
├── technique-05-ccleaner.md
├── summary.md              ← Cross-technique findings, detection recommendations, examiner guidance
└── screenshots/            ← Before and after screenshots for each technique with annotations
```

Each technique document follows this structure:
```markdown
## [Technique Name]
### What It Does
### How It Was Performed (exact commands)
### Before State (artifacts present pre-execution)
### After State (artifacts present post-execution)
### What the Examiner Can Detect
### What Cannot Be Recovered
### Detection Tools and Methods
### Examiner Recommendations
```

---

## 🔬 Project 5: Browser Artifact Parser
**Folder:** `./project-05-browser-parser/`
**When:** January – February 2027
**Type: Open Source Tool**

### What This Is
A Python command-line tool that parses forensic artifacts from all major browser SQLite databases — Chrome, Firefox, Edge, and Brave — and outputs a unified, examiner-ready CSV timeline that loads directly into Timeline Explorer. Every major browser stores history, downloads, cookies, cached login data, and form autofill in SQLite databases but the schema differs between browsers and versions. Commercial tools like Magnet AXIOM handle this well but cost thousands of dollars. Open source alternatives are fragmented and inconsistently maintained.

### Why This Matters to the Community
Small forensic firms, law enforcement agencies without budget for commercial tools, and students all need open source browser artifact parsing that produces professional output. A well-documented, actively maintained Python tool that handles multiple browsers, outputs Timeline Explorer compatible CSV, calculates artifact hashes for chain of custody purposes, and includes clear documentation would be a genuine contribution to the open source forensics ecosystem.

### Core Features to Build
- Parse Chrome, Firefox, Edge, and Brave SQLite databases from a provided evidence path
- Extract history, downloads, searches, cookies (metadata only — no content), and form autofill entries
- Normalize timestamps across browsers to UTC
- Output a unified CSV with columns compatible with Timeline Explorer
- Calculate SHA-256 hash of each source database file and include in output for chain of custody
- Generate a plain text summary report alongside the CSV
- Handle locked or corrupted database files gracefully with clear error messages
- Include a `--browser` flag to target a specific browser or default to parsing all detected

### Example Usage
```bash
python browserparse.py --evidence /path/to/user/profile --output ./results
python browserparse.py --evidence /path/to/user/profile --browser chrome --output ./results
```

### Example Output
```
results/
├── browser_timeline.csv        ← Unified timeline — all browsers, all artifact types
├── chrome_history.csv          ← Chrome-specific output
├── firefox_history.csv
├── edge_history.csv
├── brave_history.csv
├── summary_report.txt          ← Plain text summary with artifact counts and hash values
└── evidence_hashes.txt         ← SHA-256 hashes of all source database files
```

### Development Approach
Start with Chrome history only — get that working cleanly and outputting correct timestamps before adding other browsers. Then add Firefox. Then Edge and Brave. Then add the additional artifact types beyond history. Build incrementally and commit working versions at each stage so the GitHub history shows your development process.

### Deliverables
```
project-05-browser-parser/
├── README.md               ← What the tool does, installation, usage examples, output format
├── browserparse.py         ← Main tool
├── parsers/
│   ├── chrome.py
│   ├── firefox.py
│   ├── edge.py
│   └── brave.py
├── requirements.txt
├── tests/                  ← Test cases with sample database files
├── CONTRIBUTING.md         ← How others can contribute
└── LICENSE                 ← MIT license — keep it open
```

---

## 🔬 Project 6: KAPE Target Contribution
**Folder:** `./project-06-kape-target/`
**When:** March – April 2027
**Type: Direct Open Source Contribution**

### What This Is
Research a specific application or artifact category that does not yet have a KAPE Target written for it, document exactly what forensic artifacts that application leaves behind on a Windows system, and write a properly formatted KAPE Target YAML file and submit it as a pull request to the official KapeFiles repository on GitHub.

This is not a portfolio project that lives only on your GitHub. If your Target is accepted, your name goes into the contributor list of a tool that practicing examiners use in real casework every day.

### How to Find a Gap
Go to the official KapeFiles repository: [github.com/EricZimmerman/KapeFiles](https://github.com/EricZimmerman/KapeFiles)

Browse the existing Targets folder. Look for applications you use or know are common in enterprise environments that are not yet covered. Good candidates are typically:
- Communication applications — newer versions or platforms not yet covered
- Cloud storage clients — any sync application not already in the list
- Developer tools — IDEs, version control clients, package managers
- Gaming or social platforms — these increasingly appear in criminal cases

Install the application in a clean Windows VM, use it normally for a few days generating realistic activity, then image the VM and conduct a full artifact examination. Document every file, registry key, and database the application creates.

### What a KAPE Target Looks Like
```yaml
Name: ApplicationName
Description: Collects artifacts related to ApplicationName
Author: Your Name
Version: 1.0
Id: [generate a GUID]
RecreateDirectories: true
Targets:
    -
        Name: ApplicationName Database
        Category: ApplicationName
        Path: C:\Users\%user%\AppData\Roaming\ApplicationName\
        FileMask: '*.db'
        Recursive: true
        IsDirectory: false
    -
        Name: ApplicationName Logs
        Category: ApplicationName
        Path: C:\Users\%user%\AppData\Local\ApplicationName\logs\
        FileMask: '*.log'
        Recursive: true
        IsDirectory: false
```

### Objectives
- [ ] Identify a genuine gap in the KapeFiles Targets repository
- [ ] Install the target application in a clean Windows 10 VM
- [ ] Use the application normally to generate realistic forensic artifacts
- [ ] Conduct a thorough artifact examination — files created, registry keys written, databases used, network connections made, prefetch entries generated
- [ ] Document every artifact location with full path, file type, and forensic significance
- [ ] Write the KAPE Target YAML file following the official formatting standards
- [ ] Test the Target against your VM image to verify it collects what you documented
- [ ] Write a companion document explaining each artifact's forensic significance
- [ ] Submit a pull request to the official KapeFiles repository
- [ ] Respond to any reviewer feedback and iterate until accepted

### Deliverables
```
project-06-kape-target/
├── README.md               ← What application you targeted, why it matters, artifact summary
├── artifact_research.md    ← Full documentation of every artifact found and its forensic significance
├── ApplicationName.tkape   ← The KAPE Target file
├── methodology.md          ← VM setup, examination approach, testing process
└── screenshots/            ← Evidence of artifact locations and Target testing results
```

The pull request to the KapeFiles repository is the real deliverable. Everything in this folder is the research documentation that supports it.

---

## 📋 Forensic Investigation Report Schema

Every investigation report follows this structure.

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
or log entry with a timestamp. Write for someone who will fact-check
every sentence in court.

## 6. Timeline of Events
| Timestamp (UTC) | Event | Artifact Source | Confidence |
|-----------------|-------|-----------------|------------|

## 7. Indicators of Compromise
| Type | Value | First Seen | Source Artifact |
|------|-------|------------|-----------------|
(Include for incident response and malware cases.)

## 8. MITRE ATT&CK Mapping
| Tactic | Technique | Sub-Technique | ID | Observed Evidence |
|--------|-----------|---------------|----|-------------------|
(Include for incident response and malware cases. Omit for civil matters.)

## 9. Conclusions
What the evidence shows. Distinguish explicitly between what is proven
by artifact evidence and what is inferred. State your confidence level.
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

## 🌐 Practice Platforms

| Platform | Free? | Best For |
|----------|-------|----------|
| [CyberDefenders](https://cyberdefenders.org/) | ✅ Free | Forensics CTFs — one per week during semester |
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
- [ ] GitHub repository has clean structure and professional README on every project folder
- [ ] LinkedIn updated with all earned certs, DFIR skills section, and GitHub link

### Fall 2026
- [ ] Project 2 fully complete if carried over from summer
- [ ] Project 3 (NIST Hacking Case) — complete by late October
- [ ] Project 4 (Anti-Forensics Study) — complete by mid-December before finals

### Spring 2027
- [ ] Project 5 (Browser Parser) — working tool published by mid-February
- [ ] Project 6 (KAPE Target) — pull request submitted by April
- [ ] All six projects live on GitHub with clean documentation
- [ ] Internship and externship applications submitted

---

*[← Phase 4](./04-dfir-deep-dive.md) | [Back to Main Roadmap](../README.md)*
