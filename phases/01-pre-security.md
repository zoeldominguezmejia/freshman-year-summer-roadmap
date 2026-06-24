# Phase 1 — Technical Foundations
**Timeline: June 3 – June 15 | ~45 hours | ~22 hrs/week | ✅ Complete**

---

## Overview

This phase builds the baseline technical vocabulary required across all subsequent forensics work. For a digital forensics examiner, foundational knowledge has an additional dimension beyond general technical fluency: understanding *why* methodology matters, not just *how* to run a tool.

Every habit built here — documenting steps, verifying integrity, preserving originals — is a forensic habit. The examiner who understands why a JPEG starts with `FF D8 FF`, why MD5 hashes are the mechanism of chain of custody, and why deleted files are recoverable is a better examiner than one who just knows which button to press in Autopsy.

---

## Room Checklist

> **Pace guide:** ⭐ = go slow, take full notes | ➡️ = normal pace | ⚡ = complete it, move on

### Module 1: Introduction to Cyber Security
- [x] ➡️ Offensive Security Intro
- [x] ➡️ Defensive Security Intro
- [x] ➡️ Careers in Cyber
- [x] ⚡ Topic Transition Recap

### Module 2: Network Fundamentals
- [x] ➡️ What is Networking?
- [x] ➡️ Intro to LAN
- [x] ⭐ OSI Model — *understanding where data lives at each layer matters when analyzing PCAP files and network artifacts*
- [x] ⭐ Packets & Frames — *packets are what Wireshark shows you; understand the structure before you get there*
- [x] ➡️ Extending Your Network
- [x] ⚡ Topic Transition Recap

### Module 3: How The Web Works
- [x] ➡️ DNS in Detail
- [x] ⭐ HTTP in Detail — *HTTP requests and responses appear constantly in browser history artifacts and web server logs*
- [x] ➡️ How Websites Work
- [x] ➡️ Putting it all together
- [x] ⚡ Topic Transition Recap

### Module 4: Computer Fundamentals
- [x] ⭐ Inside a Computer System — *storage types, memory hierarchy, and data persistence; directly relevant to why deleted files are recoverable*
- [x] ➡️ Computer Types
- [x] ➡️ Client-Server Basics
- [x] ⭐ Virtualisation Basics — *most forensic lab work happens in VMs; understand how VM disk artifacts differ from physical machines*
- [x] ➡️ Cloud Computing Fundamentals
- [x] ⚡ Topic Rewind Recap

### Module 5: Operating Systems Basics
- [x] ⭐ Operating Systems: Introduction — *how the OS manages processes, memory, and storage is the foundation for understanding what artifacts get created and why*
- [x] ⭐ Windows Basics — *Windows generates the majority of artifacts examined in most forensic careers*
- [x] ➡️ Linux CLI Basics
- [x] ⭐ Windows CLI Basics — *command line activity leaves artifacts in Prefetch, event logs, and PowerShell history*
- [x] ⭐ Operating System Security — *every security event the OS logs is a potential artifact*
- [x] ⚡ Topic Rewind Recap

### Module 6: Software Basics
- [x] ⭐ Data Representation — *hex, binary, and ASCII are what you read when examining files in a hex editor; foundational for file carving*
- [x] ⭐ Data Encoding — *Base64 and other encodings appear constantly in malware, phishing payloads, and browser artifacts; decoded with CyberChef*
- [x] ➡️ Python: Simple Demo
- [x] ⚡ JavaScript: Simple Demo
- [x] ⭐ Database SQL Basics — *browser history, communication apps, and many OS features store data in SQLite databases; SQL lets you query them directly*
- [x] ⚡ Topic Rewind Recap

### Module 7: Attacks and Defenses
- [x] ⭐ The CIA Triad — *every forensic case ultimately comes back to a breach of confidentiality, integrity, or availability*
- [x] ⭐ Cryptography Concepts — *hash verification is how you prove evidence integrity in court; MD5 and SHA-256 are the chain of custody mechanism*
- [x] ➡️ Become a Hacker
- [x] ➡️ Become a Defender
- [x] ⚡ Topic Rewind Recap

---

## Key Takeaways for a Forensics Examiner

**Data Representation is not a side topic.** In disk forensics you read hex, understand file signatures, and identify carved files by their magic bytes. The Data Representation and Data Encoding rooms are the foundation for that work — not filler.

**Operating System Security previews artifact generation.** Every security event the OS logs — login failures, privilege escalation, process execution — is an artifact you will later hunt as an examiner. The *what gets recorded and where* is more important than the security concepts themselves at this stage.

**Cryptography Concepts is about chain of custody, not security theory.** MD5 and SHA-256 hashes are the mechanism by which you prove in court that the evidence you examined is byte-for-byte identical to what was collected. That framing matters.

---

## References

- [Gary Kessler's File Signatures Table](https://www.garykessler.net/library/file_sigs.html) — bookmark immediately; used constantly in disk forensics
- [SWGDE Best Practices](https://www.swgde.org/documents/published) — the professional standards forensic examiners are expected to follow
- [OverTheWire: Bandit](https://overthewire.org/wargames/bandit/) — Linux CLI reinforcement through a text-based game
- [SQLZoo](https://sqlzoo.net/) — SQL practice relevant to database forensics work

---

*[Back to Roadmap](../README.md) | [Phase 2 →](./02-cyber-security-101.md)*
