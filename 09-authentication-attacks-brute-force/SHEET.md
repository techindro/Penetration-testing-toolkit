# 🔐 Module 09: Authentication Protocols & Rate-Limiting Models

This module covers rate-limiting mathematical models, authentication failure thresholding, Hydra tool flag specifications, and Gobuster path discovery.

---

## 📐 1. Technical Concepts & Mathematical Models

### A. Rate-Limiting Leaky Bucket Algorithm
Security controls prevent automated brute-force attempts by enforcing bucket capacity limits $C$ and leak rates $\tau$:

$$\text{Bucket State: } B_{t+1} = \max\Big(0, \; B_t + 1 - \tau \cdot \Delta t\Big)$$

If $B_{t+1} > C$, the authentication service blocks subsequent login attempts with HTTP `429 Too Many Requests`.

---

## 🛠️ 2. Core Tool Breakdown (Hydra & Gobuster)

### A. THC-Hydra (Authentication Testing)
```bash
hydra -l admin -P /usr/share/wordlists/rockyou.txt 192.168.1.50 http-post-form "/login.php:user=^USER^&pass=^PASS^:F=Login Failed" -t 4 -V
```

#### Parameter Breakdown:
- `-l <user>` : Target single username to test.
- `-P <file>` : Path to password dictionary file.
- `http-post-form` : Module name specifying target protocol and submission format.
- `"/path:params:failure_string"` : Format string containing path, dynamic variables (`^USER^`, `^PASS^`), and string matching failure indicator (`F=...`).
- `-t <threads>` : Number of parallel execution tasks.

### B. Gobuster (Directory & Path Discovery)
```bash
gobuster dir -u https://target.com -w /usr/share/wordlists/dirb/common.txt -x php,html,json -t 20 -k
```
- `dir` : Directory enumeration mode.
- `-u <url>` : Target base URL.
- `-x <extensions>` : File extension filters to append to dictionary words.
- `-k` : Skip TLS/SSL certificate verification checks.

---

## 🛡️ 3. Authentication Hardening
- Enforce **Multi-Factor Authentication (MFA)** via FIDO2 / WebAuthn hardware security keys.
- Enforce IP-based and account-based rate limiting with CAPTCHA verification after $N$ failed attempts.
