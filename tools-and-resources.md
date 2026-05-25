# 🛠️ Tools & Resources Reference

A curated reference of everything you'll need throughout this roadmap.

---

## 🔧 Core DFIR Tools

### Disk Forensics
| Tool | Use | Link |
|------|-----|------|
| **Autopsy** | Full disk forensics GUI | https://www.autopsy.com/ |
| **FTK Imager** | Disk imaging (free) | https://www.exterro.com/ftk-imager |
| **The Sleuth Kit** | CLI disk analysis | https://www.sleuthkit.org/ |
| **Testdisk/Photorec** | File recovery | https://www.cgsecurity.org/ |
| **Foremost** | File carving | `sudo apt install foremost` |

### Memory Forensics
| Tool | Use | Link |
|------|-----|------|
| **Volatility 3** | Memory analysis framework | https://github.com/volatilityfoundation/volatility3 |
| **Volatility 2** | Legacy, some plugins not in v3 | https://github.com/volatilityfoundation/volatility |
| **Rekall** | Alternative memory framework | http://www.rekall-forensic.com/ |

### Network Forensics
| Tool | Use | Link |
|------|-----|------|
| **Wireshark** | PCAP analysis GUI | https://www.wireshark.org/ |
| **tshark** | Wireshark CLI version | `sudo apt install wireshark` |
| **NetworkMiner** | Network forensic analysis | https://www.netresec.com/?page=NetworkMiner |
| **Zeek** | Network traffic analysis | https://zeek.org/ |

### Windows Artifacts
| Tool | Use | Link |
|------|-----|------|
| **Regripper** | Windows registry parsing | https://github.com/keydet89/RegRipper3.0 |
| **Eric Zimmerman Tools** | Full suite of Windows forensics tools | https://ericzimmerman.github.io/ |
| **Chainsaw** | Windows event log hunting | https://github.com/WithSecureLabs/chainsaw |
| **Hayabusa** | Fast Windows log analysis | https://github.com/Yamato-Security/hayabusa |

### Timeline & Correlation
| Tool | Use | Link |
|------|-----|------|
| **Plaso / log2timeline** | Full system timeline creation | https://github.com/log2timeline/plaso |
| **Timeline Explorer** | GUI timeline viewer | https://ericzimmerman.github.io/ |

### All-in-One / Platforms
| Tool | Use | Link |
|------|-----|------|
| **REMnux** | Linux VM for malware analysis | https://remnux.org/ |
| **FLARE-VM** | Windows VM for malware analysis | https://github.com/mandiant/flare-vm |
| **Kali Linux** | Primary pentesting/forensics OS | https://www.kali.org/ |

---

## 📚 Learning Resources

### Free Courses & Practice
- [TryHackMe](https://tryhackme.com) — your primary platform
- [CyberDefenders](https://cyberdefenders.org/) — blue team CTF challenges
- [Blue Team Labs Online](https://blueteamlabs.online/) — SOC practice
- [LetsDefend](https://letsdefend.io/) — SOC simulations
- [PortSwigger Web Security Academy](https://portswigger.net/web-security) — web hacking

### YouTube Channels
- [13Cubed](https://www.youtube.com/@13Cubed) ⭐ — best DFIR content, free
- [John Hammond](https://www.youtube.com/@_JohnHammond) — CTF walkthroughs
- [NetworkChuck](https://www.youtube.com/@NetworkChuck) — beginner friendly networking/cybersec
- [DFIR.Science](https://www.youtube.com/@DFIRScience) — digital forensics deep dives
- [David Bombal](https://www.youtube.com/@davidbombal) — networking & cybersecurity

### Books (Free or Cheap)
- *The Art of Memory Forensics* — Gold standard memory forensics book
- *Digital Forensics with Kali Linux* — practical Kali-based guide
- [Free Security Books on GitHub](https://github.com/hackstoic/golang-open-source-projects)

### Documentation & References
- [MITRE ATT&CK](https://attack.mitre.org/) — attack framework
- [HackTricks](https://book.hacktricks.xyz/) — your hacking reference bible
- [SANS Cheat Sheets](https://www.sans.org/blog/the-ultimate-list-of-sans-cheat-sheets/) — free!
- [Forensics Wiki](https://forensics.wiki/) — artifact reference

---

## 🌐 Practice Datasets (Free)
- [NIST CFReDS](https://cfreds.nist.gov/) — official reference datasets
- [Digital Corpora](https://digitalcorpora.org/) — disk images, memory dumps
- [MemLabs](https://github.com/stuxnet999/MemLabs) — memory forensics CTF
- [MalwareBazaar](https://bazaar.abuse.ch/) — real malware samples (safe environment only)
- [VirusTotal](https://www.virustotal.com/) — online malware scanning

---

## 📝 Note-Taking Setup

Recommended: **Obsidian** (free, markdown-based, great for knowledge graphs)
- Download: https://obsidian.md/
- Template: Create a vault at `~/notes/cybersecurity/`
- One note per TryHackMe room: record commands, screenshots, key concepts

Alternative: Just use markdown files right in this GitHub repo under a `/notes` folder.

---

*[← Back to Roadmap](../README.md)*
