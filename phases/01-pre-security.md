# Phase 1 — Technical Foundations
**Timeline: June 3 – June 15 | ~45 hours | ~22 hrs/week**

---

## 🎯 Goal
Build the baseline technical and legal vocabulary needed across both practical labs and professional certification structures. For a digital forensics examiner, this phase has one additional objective beyond technical fluency: begin thinking about *why* the methodology matters, not just *how* to run a tool. Every habit you build here — documenting steps, verifying integrity, preserving originals — is a forensic habit.

---
## Why This Phase Matters

Digital forensics depends on understanding how systems normally operate before investigating how they were misused.

This phase establishes foundational knowledge in:

- Networking
- Operating Systems
- Web Technologies
- Security Concepts

Many forensic artifacts encountered later in DFIR investigations originate from concepts introduced in this phase.

## 📊 Live Master Progress Tracker & Room Checklist

> **Key:** ⭐ = go slow, take full notes | ➡️ = normal pace | ⚡ = go fast, just complete it

### Module 1: Introduction to Cyber Security
- [x] ➡️ Offensive Security Intro
- [x] ➡️ Defensive Security Intro
- [x] ➡️ Careers in Cyber
- [x] ⚡ Topic Transition Recap

### Module 2: Network Fundamentals
- [x] ➡️ What is Networking?
- [x] ➡️ Intro to LAN
- [x] ⭐ OSI Model *(understanding where data lives at each layer matters when you are analyzing PCAP files and network artifacts later)*
- [x] ⭐ Packets & Frames *(packets are what Wireshark shows you — understand what you are actually looking at before you get there)*
- [x] ➡️ Extending Your Network
- [x] ⚡ Topic Transition Recap

### Module 3: How The Web Works
- [x] ➡️ DNS in Detail
- [x] ⭐ HTTP in Detail *(HTTP requests and responses appear constantly in browser history artifacts and web server logs — understand the structure cold)*
- [x] ➡️ How Websites Work
- [x] ➡️ Putting it all together
- [x] ⚡ Topic Transition Recap

### Module 4: Computer Fundamentals
- [x] ⭐ Inside a Computer System *(storage types, memory hierarchy, and how data persists — directly relevant to understanding why deleted files are recoverable)*
- [x] ➡️ Computer Types
- [x] ➡️ Client-Server Basics
- [x] ⭐ Virtualisation Basics *(most forensic lab work happens in VMs — get comfortable with the concept and understand how VM disk artifacts differ from physical machines)*
- [x] ➡️ Cloud Computing Fundamentals
- [x] ⚡ Topic Rewind Recap

### Module 5: Operating Systems Basics
- [x] ⭐ Operating Systems: Introduction *(how the OS manages processes, memory, and storage is the foundation for understanding what artifacts get created and why)*
- [x] ⭐ Windows Basics *(the Windows OS generates the majority of artifacts you will examine in your career — pay attention to every detail covered here)*
- [x] ➡️ Linux CLI Basics
- [x] ⭐ Windows CLI Basics *(command line activity leaves artifacts in Prefetch, event logs, and PowerShell history — understand what each command does)*
- [x] ⭐ Operating System Security *(every security event the OS logs is a potential artifact — pay attention to what gets recorded and where)*
- [x] ⚡ Topic Rewind Recap

### Module 6: Software Basics
- [x] ⭐ Data Representation *(hex, binary, and ASCII are what you read when you open a file in a hex editor — you will do this regularly in disk forensics and file carving)*
- [x] ⭐ Data Encoding *(Base64 and other encodings appear constantly in malware, phishing payloads, and browser artifacts — you will decode these with CyberChef)*
- [x] ➡️ Python: Simple Demo
- [x] ⚡ JavaScript: Simple Demo *(just complete it)*
- [x] ⭐ Database SQL Basics *(browser history, communication apps, and many OS features store data in SQLite databases — SQL knowledge lets you query them directly)*
- [x] ⚡ Topic Rewind Recap

### Module 7: Attacks and Defenses
- [x] ⭐ The CIA Triad *(every forensic case ultimately comes back to a breach of confidentiality, integrity, or availability — frame every investigation around this)*
- [x] ⭐ Cryptography Concepts *(hash verification is how you prove evidence integrity in court — MD5 and SHA-256 are not just security concepts, they are your chain of custody mechanism)*
- [x] ➡️ Become a Hacker
- [x] ➡️ Become a Defender
- [x] ⚡ Topic Rewind Recap

### Enterprise Governance (UNCC Coursera Portal)
- [x] ➡️ Coursera: Google Module 1 — Foundations of Cybersecurity
- [x] ➡️ Coursera: Google Module 2 — Play It Safe: Manage Security Risks
---


## ⚖️ Examiner Mindset Notes for This Phase

**Data Representation matters more than you think.** When you get to disk forensics, you will be reading hex, understanding file signatures, and spotting deleted or carved files. The Data Encoding and Data Representation rooms in Module 6 are not filler — they are the foundation for understanding why a JPEG starts with `FF D8 FF` and why that matters when carving files from unallocated space.

**Operating System Security is a preview of artifact generation.** Every security event the OS logs — login failures, privilege escalation, process execution — is an artifact you will later hunt as an examiner. Pay attention to *what* the OS records and *where* it records it.

**Cryptography Concepts feeds directly into evidence integrity.** MD5 and SHA-256 hashes are not just security concepts — they are the mechanism by which you prove in court that the evidence you examined is identical to the evidence that was collected. Internalize why hash verification matters before you ever image a disk.

---

## 🔗 Supplemental Resources

- **Networking Visualizer:** [Cisco Packet Tracer (Free)](https://www.netacad.com/courses/packet-tracer) — Build mock LANs before diving into labs.
- **Linux Practice:** [OverTheWire: Bandit](https://overthewire.org/wargames/bandit/) — CLI command practice through a text-based game.
- **Command Reference:** [ExplainShell](https://explainshell.com/) — Paste any Linux command; get a breakdown of every flag.
- **File Signature Database:** [Gary Kessler's File Signatures Table](https://www.garykessler.net/library/file_sigs.html) — Bookmark this now. You will use it constantly in disk forensics.
- **SQL Practice:** [SQLZoo](https://sqlzoo.net/) — Relevant to Module 6 and future database forensics work.
- **Intro to Digital Evidence Law (free read):** [SWGDE Best Practices](https://www.swgde.org/documents/published) — Start skimming SWGDE documents. These are the professional standards forensic examiners are expected to follow.

---
*[← Back to Main Roadmap](../README.md) | [Phase 2 →](./02-cyber-security-101.md)*
