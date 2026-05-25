# Phase 4 — Digital Forensics Deep Dive
**Weeks 7–9 | July 7 – July 27 | ~40 hours | ~20 hrs/week**

> This is your specialty phase. You're moving from broad cybersecurity knowledge into deep DFIR expertise. These are hand-picked TryHackMe rooms focused exclusively on digital forensics skills.

---

## 🎯 Goal
Develop hands-on proficiency with the core tools and techniques used by professional digital forensic examiners — covering disk forensics, memory forensics, network forensics, mobile forensics, and log analysis.

---

## 🗺️ Forensics Domain Map

```
Digital Forensics
├── 💾 Disk Forensics        → Autopsy, FTK Imager, file system analysis
├── 🧠 Memory Forensics      → Volatility, process analysis, RAM dumps
├── 🌐 Network Forensics     → Wireshark, PCAP analysis, traffic reconstruction
├── 📱 Mobile Forensics      → iOS artifacts, Android forensics
├── 🪟 Windows Forensics     → Registry, event logs, browser artifacts, prefetch
├── 🐧 Linux Forensics       → Bash history, syslog, /proc, cron artifacts
└── 📋 Incident Response     → Chain of custody, reporting, legal considerations
```

---

## ✅ Room Checklist (All on TryHackMe)

### 💾 Disk Forensics
- [ ] [Disk Analysis & Autopsy](https://tryhackme.com/room/autopsy2ze0) — learn Autopsy tool end-to-end
- [ ] [Forensic Imaging](https://tryhackme.com/room/forensicimaging) — proper evidence acquisition
- [ ] [Intro to Cold System Forensics](https://tryhackme.com/room/introtocoldsystemforensics)

### 🧠 Memory Forensics
- [ ] [Volatility](https://tryhackme.com/room/volatility) — master Volatility 2/3 framework
- [ ] [Memory Forensics](https://tryhackme.com/room/memoryforensics) — apply Volatility to real cases
- [ ] [Advanced Endpoint Investigations](https://tryhackme.com/room/advancedendpointinvestigations) ⭐

### 🪟 Windows Forensics
- [ ] [Windows Forensics 1](https://tryhackme.com/room/windowsforensics1) — registry, user artifacts
- [ ] [Windows Forensics 2](https://tryhackme.com/room/windowsforensics2) — browser history, shellbags
- [ ] [Windows Applications Forensics](https://tryhackme.com/room/windowsapplicationsforensics)

### 🐧 Linux Forensics
- [ ] [Linux Forensics](https://tryhackme.com/room/linuxforensics) — logs, history, /proc
- [ ] [Linux Server Forensics](https://tryhackme.com/room/linuxserverforensics)

### 🌐 Network Forensics
- [ ] [Wireshark: Traffic Analysis](https://tryhackme.com/room/wiresharktrafficanalysis) — deep PCAP analysis
- [ ] [h4cked](https://tryhackme.com/room/h4cked) — investigate a real attack through PCAP

### 📱 Mobile / Specialty
- [ ] [iOS Forensics](https://tryhackme.com/room/iosforensics) — Apple device artifacts
- [ ] [Forensics (CTF Room)](https://tryhackme.com/room/forensics) — hands-on challenge with Volatility

### 🔎 Incident Response & Process
- [ ] [DFIR: An Introduction](https://tryhackme.com/room/introductoryroomdfirmodule) ⭐
- [ ] [IR Playbooks](https://tryhackme.com/room/irplaybooks)
- [ ] [IR Philosophy and Ethics](https://tryhackme.com/room/irphilosophyandethics)
- [ ] [Legal Considerations in DFIR](https://tryhackme.com/room/legalconsiderationsdfir)
- [ ] [Identification & Scoping](https://tryhackme.com/room/identificationandscoping)
- [ ] [Digital Forensics Case B4DM755](https://tryhackme.com/room/digitalforensicscase) ⭐ *(full case study)*

---

## 📝 Week-by-Week Plan

### Week 7 overlap / Week 8 (July 14 – July 20) — ~20 hrs
| Focus | Rooms |
|-------|-------|
| Disk Forensics | Forensic Imaging → Autopsy → Cold System Forensics |
| Memory Forensics | Volatility → Memory Forensics |
| Windows Forensics | Win Forensics 1 → Win Forensics 2 |

### Week 9 (July 21 – July 27) — ~20 hrs
| Focus | Rooms |
|-------|-------|
| Linux Forensics | Linux Forensics → Linux Server Forensics |
| Network Forensics | Wireshark Traffic Analysis → h4cked |
| Mobile | iOS Forensics |
| IR Process | DFIR Intro → IR Playbooks → Legal Considerations → Case B4DM755 |

---

## 🧰 Tools to Install Locally

By end of this phase, have these set up on your machine:

```bash
# On Kali Linux or a VM:
sudo apt install autopsy volatility3 wireshark sleuthkit foremost

# Or use the TryHackMe AttackBox — no local setup needed
```

**Recommended VM Setup:**
- **Kali Linux** (primary analysis machine) — free download
- **REMnux** (malware analysis) — free, pre-configured
- Use [VirtualBox](https://www.virtualbox.org/) (free) to run them

---

## 📋 Forensics Methodology Reference

Every investigation should follow this workflow:

```
1. IDENTIFICATION    → What happened? What systems are involved?
2. PRESERVATION      → Image the disk/memory — don't touch the original
3. COLLECTION        → Gather artifacts (logs, registry, browser history, etc.)
4. EXAMINATION       → Use tools to parse and extract relevant data
5. ANALYSIS          → Connect the dots — build a timeline
6. REPORTING         → Document findings clearly and completely
```

---

## 🏆 Milestones
- [ ] Complete all Phase 4 rooms
- [ ] Successfully analyze a memory dump with Volatility
- [ ] Recover deleted files from a disk image with Autopsy
- [ ] Reconstruct an attack timeline from PCAP + log data
- [ ] Write a full forensic investigation report for Case B4DM755
- [ ] Begin planning your Phase 5 project

---

## 📖 Supplemental Resources
- [The Sleuth Kit Docs](https://wiki.sleuthkit.org/) — Autopsy's underlying toolkit
- [Volatility 3 Docs](https://volatility3.readthedocs.io/)
- [SANS Digital Forensics Blog](https://www.sans.org/blog/) — industry-level write-ups
- [CyberDefenders.org](https://cyberdefenders.org/) — free blue team CTF challenges
- [13Cubed YouTube Channel](https://www.youtube.com/@13Cubed) — best free DFIR content on YouTube

---

*[← Phase 3](../03-soc-level-1/README.md) | [Back to Roadmap](../../README.md) | [Phase 5 →](../05-projects/README.md)*
