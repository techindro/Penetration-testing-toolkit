# 🎯 Module 01: Live Bug Bounty Hunting & Recon Automation

This module covers the theoretical foundations, tool flag specifications, and mathematical entropy models used for asset discovery and surface mapping in authorized security assessments.

---

## 📐 1. Theoretical Concepts & Mathematical Models

### A. Asset Discovery & Search Space Theory
When mapping an organization's external perimeter, the attack surface search space $S$ across domain hierarchies and IP space is modeled as:

$$S = D \times H \times P$$

Where:
- $D$ = Set of apex domains owned by the organization.
- $H$ = Set of active subdomains ($h_1, h_2, \dots, h_n$).
- $P$ = Set of exposed TCP/UDP network ports ($p_1, p_2, \dots, p_k$).

### B. Shannon Entropy for Secret & Parameter Detection
To identify sensitive API keys, tokens, or unique parameters in historical URL data, **Shannon Entropy** $H(X)$ is calculated over a string string $X$ of length $N$:

$$H(X) = -\sum_{i=1}^{n} P(x_i) \log_2 P(x_i)$$

Where:
- $P(x_i)$ is the probability of occurrence of character $x_i$ in the string.
- High entropy strings ($H(X) > 4.5$ for alphanumeric strings) indicate potential cryptographic keys, tokens, or hashes.

---

## 🛠️ 2. Core Reconnaissance Tools & Parameter Breakdown

### A. Subfinder (Subdomain Discovery)
Passive subdomain discovery tool that queries public logs, search engines, and passive DNS records.

```bash
subfinder -d target.com -all -silent -o subdomains.txt
```
- `-d <domain>` : Target domain name.
- `-all` : Use all available passive sources (Crt.sh, SecurityTrails, ThreatMiner, etc.).
- `-silent` : Suppress banner output for scripting pipeline integration.
- `-o <file>` : Output file path.

### B. HTTPX (HTTP Service Probing)
High-performance HTTP toolkit for probing active web services and finger-printing tech stacks.

```bash
httpx -l subdomains.txt -status-code -title -tech-detect -web-server -follow-redirects -o alive_hosts.txt
```
- `-l <file>` : Input list of hostnames/subdomains.
- `-status-code` : Display HTTP response status codes (200, 301, 403, 500, etc.).
- `-title` : Extract HTML `<title>` tag from target web pages.
- `-tech-detect` : Fingerprint backend technologies (Wappalyzer library integration).
- `-follow-redirects` : Follow HTTP 301/302 redirect chains.

### C. Nuclei (Template-Based Security Auditing)
Vulnerability scanner driven by community-curated YAML security check templates.

```bash
nuclei -l alive_hosts.txt -severity high,critical -t misconfiguration/ -o nuclei_results.txt
```
- `-severity <levels>` : Filter templates by severity rating (`info`, `low`, `medium`, `high`, `critical`).
- `-t <dir>` : Target template directory (e.g., misconfigurations, exposed-panels, CVEs).

---

## 🛡️ 3. Defensive Recommendations (CIS Benchmarks & OWASP)
- **Wildcard DNS Management:** Remove obsolete wildcard (`*.target.com`) DNS A/CNAME records.
- **Port Visibility:** Enforce perimeter firewalls (AWS Security Groups, Cloudflare Magic Transit) to block unneeded public ports.
