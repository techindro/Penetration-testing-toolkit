# 🐉 Module 06: Kali Linux Essential Security Tools CLI Cheatsheet

Quick-reference syntax cheat-sheet for widely used security auditing and network analysis CLI tools installed in Kali Linux.

---

## 🎯 1. Network Discovery & Scanning (`nmap`)

```bash
# Fast SYN Stealth Scan on top 1000 ports with OS & service detection
nmap -sS -sV -O <target-ip>

# Scan specific ports with default NSE security scripts
nmap -p 22,80,443 -sC -sV <target-ip>

# Fast Ping Sweep across entire subnet
nmap -sn 192.168.1.0/24
```

---

## 🔍 2. Web Subdomain & Directory Discovery (`subfinder`, `httpx`, `gobuster`, `ffuf`)

```bash
# Passive subdomain discovery
subfinder -d target.com -o subdomains.txt

# Probe active HTTP hosts and status codes
httpx -l subdomains.txt -status-code -title -o alive.txt

# Directory brute-forcing with Gobuster
gobuster dir -u https://target.com -w /usr/share/wordlists/dirb/common.txt

# High-speed API endpoint fuzzing with FFUF
ffuf -w /usr/share/wordlists/dirb/common.txt -u https://target.com/FUZZ -mc 200,403
```

---

## 🔐 3. Password Audit & Hash Processing (`hashcat`, `john`, `hydra`)

```bash
# Hashcat NTLMv2 hash auditing
hashcat -m 5600 hashes.txt /usr/share/wordlists/rockyou.txt

# John the Ripper hash cracking
john --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt

# Hydra login form auditing
hydra -l admin -P /usr/share/wordlists/rockyou.txt <target-ip> http-post-form "/login.php:user=^USER^&pass=^PASS^:Login Failed"
```

---

## 📦 4. Packet Capture & Firmware Analysis (`tshark`, `binwalk`)

```bash
# Capture packets on interface wlan0 and filter port 80
tshark -i wlan0 -f "tcp port 80"

# Extract file system archives from firmware image
binwalk -e firmware.bin
```
