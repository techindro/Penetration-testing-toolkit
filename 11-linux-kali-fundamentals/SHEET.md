# 🐧 Module 11: Linux & Kali Linux Essentials for Security Auditing

This module provides a complete reference guide to Linux administration, networking commands, text processing utilities, and Kali Linux environment management required for ethical security analysis.

---

## 📌 1. Linux File System & Navigation

| Command | Description | Example |
| :--- | :--- | :--- |
| `pwd` | Print current working directory | `pwd` |
| `ls -la` | List all files including hidden files with permissions | `ls -la /var/www/html` |
| `cd` | Change directory | `cd /etc/nginx/` |
| `file` | Determine file type by inspecting header bytes | `file firmware.bin` |
| `find` | Search files by name, size, or permissions | `find / -perm -4000 2>/dev/null` (Find SUID binaries) |
| `stat` | Display detailed file status & timestamps | `stat /etc/passwd` |

---

## 🔒 2. File Permissions & Ownership

Linux uses 9 permission bits grouped into User (u), Group (g), and Others (o):

```
- rwx r-x r--  1 root root  1024 Jan 1 00:00 script.sh
  │││ │││ │││
  │││ │││ └── Others: Read (4)
  │││ └────── Group: Read (4) + Execute (1) = 5
  └────────── User: Read (4) + Write (2) + Execute (1) = 7
```

```bash
# Set rwxr-xr-x (755) permissions
chmod 755 script.sh

# Change file owner and group
chown root:root script.sh

# Set SUID bit (Execution with file owner privileges)
chmod u+s /usr/local/bin/custom_tool
```

---

## ⚡ 3. Text Processing & Data Extraction

Security auditing requires filtering large log files, output streams, and wordlists:

```bash
# Grep: Search for patterns in text files
grep -rn "API_KEY" /var/log/app/

# Sort & Uniq: Deduplicate lines in target lists
cat subdomains.txt | sort -u > unique_subs.txt

# Awk: Extract specific columns (e.g., column 1 and 3)
awk '{print $1, $3}' access.log

# Sed: Search and replace strings
sed -i 's/http:/https:/g' urls.txt

# Cut: Extract character ranges or delimited fields
cut -d ',' -f 2-3 users.csv
```

---

## 📡 4. Networking & Service Management

```bash
# Inspect network interface configuration
ip a  # or ifconfig

# Inspect active TCP/UDP listening ports and processes
netstat -tulpn  # or ss -tulpn

# Monitor active network connections in real-time
ss -ta

# Check DNS resolution for a domain
dig target.com ANY +short

# Verify network route to host
traceroute target.com

# Service Management (systemd)
sudo systemctl status nginx
sudo systemctl start postgresql
sudo systemctl stop apache2
```

---

## 🛡️ 5. Kali Linux Package Management & Tool Setup

```bash
# Update package list and upgrade installed tools
sudo apt update && sudo apt upgrade -y

# Install essential pentesting packages
sudo apt install -y build-essential curl wget git nmap tshark python3-pip

# Search for Kali tools in apt repositories
apt search security-tool-name
```
