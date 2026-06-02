# Phase 5 — DFIR Projects & Professional Portfolio
**Timeline: August 10 – August 16 | ~40 hours | ~20 hrs/week**

---

## 🎯 Goal
Synthesize your technical TryHackMe abilities and the professional documentation principles taught in your UNCC Coursera courses into production-grade portfolio pieces. These documents will form the foundation of your interview talking points during your upcoming sophomore year hiring cycles.

---

## 📁 Summer Capstone Deliverables

| Project | Focus Area | TryHackMe Lab Context | Coursera Context |
|---|---|---|---|
| **1. Ransomware Investigation** | Disk + Memory + Network | Volatility & Autopsy Rooms | Incident Response Frameworks |
| **2. Insider Threat Registry Hunt** | Registry & USB Artifacts | Windows Forensics 1 & 2 | Asset Protection & Privacy|

---

## 🔬 Project Strategy for Sophomores

To ensure these projects survive a rigorous technical resume screening, you must execute them following the industry-standard **NIST SP 800-61 r2** playbook formats introduced during your Coursera certificate modules.

### Formatting Requirements:
* **The Code:** Save all forensic artifact parsing commands (Volatility plugins used, RegRipper script strings) into clean `.sh` or `.ps1` files inside your repository folders.
* **The Report:** Avoid informal write-ups. Use the **Litigation-Ready Forensic Format** defined below for both Project 1 and Project 2.

---

## 📋 Professional Forensic Report Schema

Every project repository folder must house a markdown document structured exactly as follows:

```markdown
# Forensic Investigation Report (NIST Compliance)

## 1. Executive Summary
Brief non-technical overview summarizing the scope, impact of the incident, and key absolute confirmations.

## 2. Chain of Custody & Evidence Hashes
Verification hashes (SHA-256) of the disk images, network PCAPs, or memory dumps utilized to ensure integrity.

## 3. Tooling & Environment Inventory
Explicit listing of forensic software used (e.g., Volatility 3 v2.4.1, Autopsy GUI v4.21.0).

## 4. Analytical Findings & Timeline Reconstructions
Chronological breakdown connecting specific system events, compromised registry values, and active processes back to malicious activities.

## 5. MITRE ATT&CK Technique Mappings
Granular mapping of the attacker actions to specific tactics and sub-techniques.

## 6. Containment & Eradication Strategy
Actionable remediation and defense configurations based on discovered Indicators of Compromise (IOCs).
```
## 🏆 End of Summer Checkpoint (August 16 Deadline)
- [ ] Push clean repository folders containing evidence artifacts, reports, and code scripts.
- [ ] Pin your top Forensic Report to your GitHub profile front-page.
- [ ] Link your Google Cybersecurity Professional Certificate badge directly to your LinkedIn profile.

---

*[← Phase 4](./04-dfir-deep-dive.md) | [Back to Main Roadmap](../README.md)*
