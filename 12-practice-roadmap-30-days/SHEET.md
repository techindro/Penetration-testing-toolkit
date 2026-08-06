# 📅 Module 12: 30-Day Ethical Hacking Practice & Learning Roadmap

This structured 30-day curriculum provides a step-by-step roadmap for studying security auditing, Linux administration, web app security, network protocols, and bug bounty report writing.

---

## 🗓️ Phase 1: Linux, Networking & HTTP Fundamentals (Days 1–7)

### Day 1: Linux CLI & Environment Mastery
- **Topics:** File navigation (`ls`, `cd`, `find`), SUID/SGID permissions (`chmod`, `chown`).
- **Lab Practice:** Solve Linux basics rooms on PortSwigger / TryHackMe.
- **Reference:** [Module 11: Linux & Kali Fundamentals](../11-linux-kali-fundamentals/README.md)

### Day 2: Text Processing & Scripting Basics
- **Topics:** Processing logs with `grep`, `awk`, `sed`, `sort`, `uniq`.
- **Practice:** Write a bash script to filter and deduplicate IP addresses from a sample web server log file.

### Day 3: Networking Protocols & Wireshark
- **Topics:** OSI model, TCP 3-way handshake, UDP vs TCP, DNS query resolution.
- **Practice:** Capture local HTTP traffic using Wireshark and inspect TCP headers.

### Day 4: HTTP/HTTPS Protocol & Request/Response Lifecycle
- **Topics:** HTTP Methods (`GET`, `POST`, `PUT`, `DELETE`), Request Headers (`Host`, `Authorization`, `Cookie`), Status Codes (`200`, `301`, `401`, `403`, `500`).
- **Practice:** Inspect network traffic using browser Developer Tools (F12) Network tab.

### Day 5: Web Architecture & Client-Side vs Server-Side Logic
- **Topics:** DOM, JavaScript sinks, HTML rendering, Cookies, LocalStorage, SessionStorage.

### Day 6: Cryptography Basics & Hashes
- **Topics:** Hashing (`MD5`, `SHA256`, `bcrypt`), Symmetric vs Asymmetric Encryption (`AES`, `RSA`), TLS/SSL certificates.
- **Practice:** Generate SHA-256 hashes of text strings using `sha256sum`.

### Day 7: Phase 1 Review & Knowledge Check
- **Task:** Review PortSwigger Web Security Academy introductory materials.

---

## 🗓️ Phase 2: Web Application Security (Days 8–18)

### Day 8: Information Gathering & Recon Theory
- **Topics:** Passive DNS enumeration, WHOIS lookup, subdomains.
- **Reference:** [Module 01: Recon Automation](../01-live-bug-bounty-automation/README.md)

### Day 9: Cross-Site Scripting (XSS) - Reflected & Stored
- **Topics:** HTML Body Context, Attribute Context, Output Encoding.
- **Reference:** [Module 02: Web App Exploitation](../02-web-app-exploitation/README.md)

### Day 10: DOM-Based XSS & Source-Sink Mapping
- **Topics:** Unsafe JavaScript sources (`location.hash`) and sinks (`innerHTML`, `eval`).
- **Practice:** Complete PortSwigger DOM XSS labs.

### Day 11: SQL Injection (SQLi) - In-Band & Boolean
- **Topics:** SQL syntax trees, boolean logic statements, parameterized queries.
- **Reference:** [Module 02: Web App Exploitation](../02-web-app-exploitation/README.md)

### Day 12: SQL Injection - Time-Based & Blind SQLi
- **Topics:** Database sleep functions (`SLEEP()`, `WAITFOR DELAY`), inference logic.

### Day 13: Broken Access Control (IDOR / BOLA)
- **Topics:** User session validation, horizontal vs vertical privilege escalation.
- **Practice:** Audit API endpoint parameters for authorization checks.

### Day 14: Cross-Site Request Forgery (CSRF) & SameSite Cookies
- **Topics:** Anti-CSRF tokens, `SameSite=Strict/Lax` cookie flags.

### Day 15: API Security & JWT Tokens
- **Topics:** JWT Base64URL structure, signature algorithms (`HS256`, `RS256`), algorithm bypass theory.
- **Reference:** [Module 03: API Security](../03-api-security-token-manipulation/README.md)

### Day 16: Parameter & Directory Fuzzing
- **Topics:** FFUF / Gobuster setup, rate-limiting leaky bucket algorithm.
- **Reference:** [Module 09: Authentication Attacks](../09-authentication-attacks-brute-force/README.md)

### Day 17: Server-Side Request Forgery (SSRF) Basics
- **Topics:** Internal service binding, loopback IP addresses (`127.0.0.1`), IMDS metadata endpoint protection.
- **Reference:** [Module 04: Cloud Security AWS](../04-cloud-security-aws/README.md)

### Day 18: Phase 2 Review & PortSwigger Labs Practice
- **Task:** Complete 5 PortSwigger Web Security Academy labs (Apprentice level).

---

## 🗓️ Phase 3: Infrastructure, Mobile & Cloud Security (Days 19–25)

### Day 19: Wireless Security Protocols
- **Topics:** WPA2 4-Way Handshake, PMK/PTK key derivation math, WPA3 SAE.
- **Reference:** [Module 05: Wireless Auditing](../05-wireless-auditing/README.md)

### Day 20: Network Protocols & Security Controls
- **Topics:** ARP header layout, Dynamic ARP Inspection (DAI) switch configuration.
- **Reference:** [Module 07: Network Protocols](../07-network-spoofing-mitm/README.md)

### Day 21: Active Directory Security Concepts
- **Topics:** Kerberos authentication protocol, NTLMv2 HMAC-MD5 hash derivation.
- **Reference:** [Module 08: Active Directory Windows](../08-active-directory-windows/README.md)

### Day 22: IoT Firmware Static Analysis
- **Topics:** Firmware magic bytes, filesystem archives (`SquashFS`), static code inspection.
- **Reference:** [Module 06: IoT CCTV Firmware](../06-iot-cctv-firmware-auditing/README.md)

### Day 23: Cloud Storage Security (AWS S3)
- **Topics:** S3 Access Policies, IAM roles, Block Public Access configuration.
- **Reference:** [Module 04: Cloud Security AWS](../04-cloud-security-aws/README.md)

### Day 24: Mobile App Security Fundamentals (Android)
- **Topics:** APK structure, Android Network Security Configuration XML, SSL Pinning.
- **Reference:** [Module 10: Mobile Sec](../10-mobile-sec-kernelsu/README.md)

### Day 25: Dynamic Instrumentation Concepts (Frida)
- **Topics:** V8 JavaScript engine injection, process hooking mechanics.

---

## 🗓️ Phase 4: Authorized Bug Bounty & VDP Reporting (Days 26–30)

### Day 26: Rules of Engagement & Scope Verification
- **Topics:** Reading VDP policies (e.g. NASA VDP), identifying in-scope assets, legal authorization boundaries.

### Day 27: Vulnerability Assessment & PoC Documentation
- **Topics:** Writing clear, reproducible Proof-of-Concept (PoC) steps without exploiting or modifying data.

### Day 28: CVSS v3.1 / v4.0 Scoring Methodology
- **Topics:** Attack Vector (AV), Attack Complexity (AC), Privileges Required (PR), User Interaction (UI), Scope (S), Impact (C/I/A).

### Day 29: Writing Professional Security Reports
- **Topics:** Report structure: Executive Summary, Vulnerability Details, Steps to Reproduce, Remediation Recommendations.

### Day 30: Continuous Learning & Community Integration
- **Topics:** Open Source Tool integrations, OWASP community guidelines, legal bug bounty platforms (HackerOne, Bugcrowd).
