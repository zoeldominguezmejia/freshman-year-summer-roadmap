# 🔍 Digital Forensics Examiner Roadmap — UNCC Summer After Freshman Year
### Goal: Digital Forensics Examiner (Law Enforcement / Private Sector / Corporate Investigations)
**Start Date:** June 2, 2026 | **Target Date:** August 18 (Fall Semester Begins)
**Last Updated:** June 3, 2026

---

## 📋 About This Roadmap

A structured, dual-track roadmap combining hands-on forensic labs via **TryHackMe Premium** with professional certifications through the **UNCC Coursera Career Academy** (free) — built specifically for the path to becoming a **digital forensics examiner**, not a generalist SOC analyst.

Digital forensics examiners operate in law enforcement agencies, private forensic firms, corporate legal departments, and government agencies. The job demands technical precision, legally defensible methodology, documentation discipline, and an understanding of how digital evidence is treated in court. Your Criminal Justice minor is not a checkbox — it is a genuine differentiator that most technically-trained candidates do not have.

**Platforms:** [TryHackMe Premium](https://tryhackme.com) & [UNCC Coursera Career Academy](https://coursera.org)
**Primary Goal:** Forensic Examiner Portfolio + Internship/Externship Readiness
**Credentials Targeted:** Google Cybersecurity Certificate, CompTIA Security+, CompTIA CySA+, EnCE (long-term)

---

## 🗂️ Strategic Roadmap Overview

| Phase | Content | Timeline | Est. Hours | Weekly Pace |
|-------|---------|----------|------------|-------------|
| **Phase 1** | Pre-Security Path (7 modules) + Google Modules 1–2 | June 3 – June 15 | ~45 hrs | ~22 hrs/week |
| **Phase 2** | Cyber Security 101 (14 sections) + Google Modules 3–4 | June 16 – July 10 | ~55 hrs | ~17 hrs/week |
| **Phase 3** | SOC Level 1 (14 sections) + Google Modules 5–7 | July 11 – July 29 | ~50 hrs | ~17 hrs/week |
| **Phase 4** | DFIR Deep Dive + Google Module 8 | July 30 – Aug 12 | ~40 hrs | ~20 hrs/week |
| **Phase 5** | DFIR Portfolio Projects 1 & 2 | Aug 13 – Aug 17 + early semester | ~20 hrs first sprint | ~20 hrs/week |

**Total summer hours: ~210 hours across 11 weeks**

---

## 📅 Full Summer Calendar

| Week | Dates | Phase | Primary Focus |
|------|-------|-------|---------------|
| Week 1 | June 3–8 | Phase 1 | Computer Fundamentals (today), OS Basics, Google Module 1 |
| Week 2 | June 9–15 | Phase 1 | Software Basics, Attacks & Defenses, Google Module 2 → **SEC0 cert** |
| Week 3 | June 16–22 | Phase 2 | Linux, Windows + AD, Command Line |
| Week 4 | June 23–29 | Phase 2 | Networking tools, Cryptography, Exploitation basics |
| Week 5 | June 30–July 6 | Phase 2 | Web Hacking, Forensics Fundamentals deep pass |
| Week 6 | July 7–10 | Phase 2 | Defensive sections, SIEM intro → **SEC1 cert** |
| Week 7 | July 11–17 | Phase 3 | SOC Fundamentals, Frameworks, Phishing Analysis |
| Week 8 | July 18–24 | Phase 3 | Network/Windows/Linux Monitoring, Malware Concepts |
| Week 9 | July 25–29 | Phase 3 | Threat Intel, SIEM Triage, Boogeyman capstones → **SAL1 cert** |
| Week 10 | July 30–Aug 5 | Phase 4 | DFIR Intro, Windows Forensics, Linux Forensics, Autopsy |
| Week 11 | Aug 6–12 | Phase 4 | Volatility, KAPE, Redline, Capstone rooms → **Google cert** |
| Final sprint | Aug 13–17 | Phase 5 | Projects 1 & 2 (continue into first weeks of semester) |

---

## 📁 Repo Structure

```text
cybersecurity-roadmap/
├── README.md
├── resources/
│   └── tools-and-resources.md
└── phases/
├── 01-pre-security/
├── 02-cybersecurity-101/
├── 03-soc-level-1/
├── 04-dfir-deep-dive/
├── 05-projects/
└── 06-sophomore-year/
├── fall-2026.md
└── spring-2027.md
```

---

## 🎓 Full Certification Roadmap

| Cert | Platform | When | Cost | Why It Matters |
|------|----------|------|------|----------------|
| SEC0 Pre-Security | TryHackMe | ~June 14 | Free (Premium) | Baseline foundation |
| SEC1 Cyber Security 101 | TryHackMe | ~July 9 | Free (Premium) | Broad technical fluency |
| SAL1 SOC Analyst Level 1 | TryHackMe | ~July 28 | Free (Premium) | Evidence triage and log analysis |
| Google Cybersecurity Professional Certificate | Coursera/UNCC | ~Aug 11 | Free (UNCC) | Foundational credential, LinkedIn visibility |
| CompTIA Security+ SY0-701 | CompTIA | Nov–Dec 2026 | ~$392 | HR filter cert — required at most agencies |
| CompTIA CySA+ CS0-003 | CompTIA | Apr–May 2027 | ~$392 | Analyst-level cert, bridges to forensics |
| EnCE (EnCase Certified Examiner) | OpenText | Summer 2027+ | ~$400 | The gold standard examiner credential |
| GCFE (GIAC Certified Forensic Examiner) | GIAC/SANS | Post-graduation goal | ~$2,499 | Court-recognized, opens law enforcement doors |
| GCFA (GIAC Certified Forensic Analyst) | GIAC/SANS | Long-term goal | ~$2,499 | Advanced IR + forensics — senior examiner tier |

> **Note on EnCE vs GCFE:** EnCE is more accessible and widely recognized in private sector and corporate forensics. GCFE is the credential that opens law enforcement lab doors. Target EnCE first, GCFE after you have a job and potential employer funding.

---

## 🛠️ Tools You Will Learn

### Primary Examiner Tools
- **Autopsy** — Open-source disk forensics GUI; the free examiner's workhorse
- **FTK Imager** — Forensically sound disk imaging; free and industry standard
- **Magnet AXIOM** — Industry-leading commercial forensics platform (trial during Phase 4)
- **EnCase** — The other dominant commercial platform (trial available)
- **Volatility 3** — Memory forensics framework
- **KAPE** — Rapid artifact triage and collection (Kroll)
- **Redline** — Endpoint memory and IOC analysis (Mandiant)

### Evidence & Artifact Tools
- **Eric Zimmerman Tools** — Complete Windows artifact suite (ShellBags Explorer, JLECmd, LECmd, MFTECmd, PECmd, RECmd, and more)
- **Regripper** — Windows registry parsing
- **Plaso / log2timeline** — Full supertimeline creation
- **Timeline Explorer** — GUI timeline viewer (EZ Tools)
- **Chainsaw / Hayabusa** — Windows event log hunting and threat detection

### Network & Analysis
- **Wireshark / tshark** — PCAP analysis
- **NetworkMiner** — Network forensic artifact extraction
- **CyberChef** — IOC decoding, encoding, and data transformation

### Malware Analysis Environment
- **REMnux** — Linux-based malware analysis VM
- **FLARE-VM** — Windows-based malware analysis environment
- **Any.run** — Interactive online sandbox

### Case Management
- **TheHive** — Incident response and case management
- **Magnet AUTOMATE** — Workflow automation for examiner labs (enterprise)

---

## ⚖️ Why Your CJ Minor Changes Everything

Most people entering digital forensics come from pure CS or cybersecurity programs. They understand the tools but not the legal framework around them. Your Criminal Justice minor gives you:

- **Rules of evidence** — What makes digital evidence admissible vs. inadmissible
- **Chain of custody** — How to handle, document, and transfer evidence without tainting it
- **Expert witness standards** — What Daubert and Frye standards mean for forensic tool validation
- **Legal system literacy** — How your reports will actually be used in criminal and civil proceedings
- **Agency context** — Understanding how law enforcement forensic labs operate vs. private firms

This combination of technical training and legal context is exactly what law enforcement agencies, prosecutors' offices, and corporate legal departments hire for. Lead with it.

---

*Last updated: June 3, 2026*
