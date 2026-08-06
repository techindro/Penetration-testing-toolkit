# 🐧 BugFix FM - Linux & Kali Linux Master Command Booklet
> **A Comprehensive Command Reference & Cheatsheet for Computer Science & Engineering Students.**

Curated by **Shubham Patel (techindro)**

**⚠️ DISCLAIMER:** This booklet is strictly for educational purposes, authorized research, and defensive security auditing. Performing unauthorized attacks or scanning networks without explicit, written permission/scope is completely illegal and punishable by law.

---

## 📌 Master Command Cheatsheet Index

| Module | Topic / Focus Area | Frequently Forgotten Commands & Solved Bugs | Cheatsheet Link |
| :--- | :--- | :--- | :---: |
| **01. File System & Permissions** | File Search & Security Bits | `find` (SUID/size/name), `chmod 755`/`4755`, `chown`, `tar`, `df -h`, `stat` | [View Cheatsheet](01-file-system-and-permissions/SHEET.md) |
| **02. Text Processing & Parsing** | Data Extraction & Editing | `grep -rn`, `awk -F ':'`, `sed -i 's///g'`, `sort \| uniq -c`, `cut -d` | [View Cheatsheet](02-text-processing-grep-awk-sed/SHEET.md) |
| **03. Networking & Firewall** | Ports, DNS & HTTP Testing | `ip a`, `ss -tulpn`, `dig ANY`, `curl -X POST`, `wget -c`, `ufw allow` | [View Cheatsheet](03-networking-ports-firewall/SHEET.md) |
| **04. Process & Resource Control** | Systemd, Logs & Backgrounding | `ps aux`, `kill -9`, `systemctl status/restart`, `journalctl -u -f`, `free -h` | [View Cheatsheet](04-process-systemd-resource-monitoring/SHEET.md) |
| **05. Users, Groups & Sudo** | Privileges & Environment Groups | `whoami`, `id`, `usermod -aG (docker/dialout/sudo)`, `sudo -l`, `visudo` | [View Cheatsheet](05-users-groups-sudo-permissions/SHEET.md) |
| **06. Kali Security Tools** | Audit & Recon CLI Tools Syntax | `nmap -sS -sV`, `subfinder`, `httpx`, `gobuster`, `ffuf`, `hashcat`, `hydra` | [View Cheatsheet](06-kali-security-tools-cheatsheet/SHEET.md) |

---

## 📂 Repository Directory Structure

```
BugFix-FM-Linux-Booklet/
├── 01-file-system-and-permissions/        # SHEET.md (find, chmod, SUID, tar, df, du)
├── 02-text-processing-grep-awk-sed/       # SHEET.md (grep, awk, sed, sort, uniq, cut)
├── 03-networking-ports-firewall/          # SHEET.md (ip, ss, netstat, dig, curl, ufw)
├── 04-process-systemd-resource-monitoring/ # SHEET.md (ps, kill, systemctl, journalctl, free)
├── 05-users-groups-sudo-permissions/       # SHEET.md (id, usermod -aG, sudo -l, visudo)
├── 06-kali-security-tools-cheatsheet/     # SHEET.md (nmap, subfinder, httpx, ffuf, hydra)
└── README.md                              # Master Command Booklet Index
```

---
**🐧 BugFix FM Maintainer:** [Shubham Patel (techindro)](https://github.com)
