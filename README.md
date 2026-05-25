# 🛡️ DFIR Learning Roadmap & Portfolio

Welcome to my **Digital Forensics and Incident Response (DFIR)** journey. This repository documents a structured, 11-week intensive roadmap designed to build foundational cybersecurity knowledge and transition into specialized forensic analysis.

---

## 🗺️ Roadmap Overview

This path is divided into five distinct phases, moving from the basics of how computers communicate to advanced memory and disk forensics.

| Phase | Title | Focus Area | Timeline |
|:---:|:---|:---|:---|
| **1** | [Pre-Security](./phases/01-pre-security.md) | Networking, OS, & Web Fundamentals | May 25 – June 8 |
| **2** | [Cyber Security 101](./phases/02-cyber-security-101.md) | Red & Blue Team Basics | June 9 – June 29 |
| **3** | [SOC Level 1](./phases/03-soc-level-1.md) | SIEM, Logs, & Threat Intel | June 23 – July 13 |
| **4** | [Digital Forensics Deep Dive](./phases/04-digital-forensics-deep-dive.md) | Advanced Forensics Tools | July 7 – July 27 |
| **5** | [Starter Projects](./phases/05-projects.md) | Real-world Investigations | July 28 – Aug 13 |

---

## 🛠️ The Toolkit

Throughout this roadmap, I utilize industry-standard tools to analyze artifacts and reconstruct attack chains.

* **Disk Forensics:** Autopsy, FTK Imager, and The Sleuth Kit.
* **Memory Forensics:** Volatility 3 and Rekall.
* **Network Forensics:** Wireshark, Zeek, and NetworkMiner.
* **Windows Artifacts:** Eric Zimmerman's Tools, Hayabusa, and RegRipper.

> [!NOTE]
> For a full list of software and learning materials, see the [Tools & Resources Reference](./tools-and-resources.md).

---

## 🔬 Featured Portfolio Projects

Phase 5 represents the culmination of this training, where I apply forensic methodologies to simulated real-world incidents.

### 1. Ransomware Attack Investigation
* **Objective:** Identify malicious processes in memory dumps and find dropped artifacts in disk images.
* **Tools:** Volatility, Autopsy.

### 2. Insider Threat Investigation
* **Objective:** Track evidence of data exfiltration via USB and personal email.
* **Focus:** Windows Registry (USBSTOR), LNK files, and Shellbags.

---

## 📝 Forensic Methodology

Every investigation in this repository follows a standard forensic workflow to ensure data integrity:

1.  **Identification:** Scoping the incident and identifying involved systems.
2.  **Preservation:** Imaging disk and memory without altering original evidence.
3.  **Collection:** Extracting artifacts like logs, registry hives, and browser history.
4.  **Examination & Analysis:** Using specialized tools to parse and extract relevant data.
5.  **Reporting:** Documenting findings in a clear, factual, and reproducible manner.

---
*This roadmap is based on a curated selection of TryHackMe rooms and open-source forensic tools.*
