# 🛡️ Module 35: OWASP Top 10 Security Vulnerabilities & Remediation Cheatsheet (30 Items)

Complete reference for the OWASP Top 10 Web Application Security Vulnerabilities, attack descriptions, code indicators, and defensive remediation cheatsheets categorized by difficulty level (🟢 Easy, 🟡 Medium, 🔴 Hard).

---

## 🟢 Level 1: Core OWASP Top 10 Concepts (1 - 10)

```
1. A01:2021 - Broken Access Control
   - Description: Users can access data or perform actions outside their intended permissions.
   - Example: Changing URL parameter ID from /user?id=101 to /user?id=102 to view another user's profile.

2. A02:2021 - Cryptographic Failures
   - Description: Sensitive data in transit or at rest is exposed due to weak encryption or plain text storage.
   - Example: Storing passwords in plain text or using MD5 / SHA1 hashing instead of bcrypt / Argon2id.

3. A03:2021 - Injection (SQL Injection, Command Injection, XSS)
   - Description: Untrusted user input is executed directly as code or SQL query by interpreter.
   - Example: Entering ' OR 1=1 -- into a login username field to bypass authentication.

4. A04:2021 - Insecure Design
   - Description: Flaws in architectural design and lack of threat modeling before coding.
   - Example: Recovery flow allowing password resets without verification questions or MFA.

5. A05:2021 - Security Misconfiguration
   - Description: Unhardened default configurations, verbose debug stack traces exposed in production.
   - Example: Leaving default admin credentials (admin/admin) active on router or database server.

6. A06:2021 - Vulnerable and Outdated Components
   - Description: Running libraries, frameworks, or dependencies with known security CVE vulnerabilities.
   - Example: Running Log4j version 2.14 (Log4Shell vulnerability).

7. A07:2021 - Identification and Authentication Failures
   - Description: Weak session management, lack of rate limiting allowing brute force attacks.
   - Example: Session tokens not invalidated upon logout or expired.

8. A08:2021 - Software and Data Integrity Failures
   - Description: Code and plugins used without verifying digital signatures or integrity hashes.
   - Example: Insecure deserialization allowing remote code execution.

9. A09:2021 - Security Logging and Monitoring Failures
   - Description: Insufficient logging of security events (e.g. failed logins) making detection impossible.
   - Example: Security breaches occurring undetected for months due to missing central audit logs.

10. A10:2021 - Server-Side Request Forgery (SSRF)
   - Description: Server fetches remote resource requested by client without validating destination URL.
   - Example: Injecting http://169.254.169.254/latest/meta-data/ into image fetch URL to extract AWS IAM keys.
```

---

## 🟡 Level 2: Defensive Remediation Code Templates (11 - 20)

```python
# 11. SQL Injection Prevention: Use Prepared Statements / Parameterized Queries
# ❌ VULNERABLE: cursor.execute(f"SELECT * FROM users WHERE username = '{user_input}'")
# ✅ SECURE:
cursor.execute("SELECT * FROM users WHERE username = %s", (user_input,))

# 12. Password Hashing: Use Bcrypt with High Work Factor
import bcrypt
salt = bcrypt.gensalt(rounds=12)
hashed_password = bcrypt.hashpw(password.encode('utf-8'), salt)

# 13. Cross-Site Scripting (XSS) Prevention: Sanitize / Escape Output HTML
import html
safe_user_comment = html.escape(user_comment)

# 14. Secure Cookie Flags (HttpOnly, Secure, SameSite)
# Set-Cookie: session_id=xyz123; Secure; HttpOnly; SameSite=Strict; Path=/

# 15. Cross-Site Request Forgery (CSRF) Protection
# Include random anti-CSRF token in HTTP POST forms and validate server-side.

# 16. Enforce Content Security Policy (CSP) Header
# Content-Security-Policy: default-src 'self'; script-src 'self' https://trustedscripts.com;

# 17. HTTP Strict Transport Security (HSTS) Header
# Strict-Transport-Security: max-age=31536000; includeSubDomains; preload

# 18. Disable Verbose Production Server Banner Headers (Server Tokens)
# Nginx config: server_tokens off;
# Express config: app.disable('x-powered-by');

# 19. Implement Rate Limiting on Authentication Endpoints
# Limit login attempts to max 5 failures per 15 minutes per IP address.

# 20. Prevent SSRF: Restrict Outbound Server Connections via URL Whitelisting
allowed_domains = ['api.trustedpartner.com']
```

---

## 🔴 Level 3: Security Auditing Commands & Best Practices (21 - 30)

```bash
# 21. Audit Python dependencies for CVE security vulnerabilities
pip install safety && safety check

# 22. Audit Node.js NPM dependencies for CVE vulnerabilities
npm audit --audit-level=high

# 23. Perform Static Application Security Testing (SAST) on Python code
pip install bandit && bandit -r ./src

# 24. Verify SSL/TLS Certificate & Cipher suite strength on web server
nmap --script ssl-enum-ciphers -p 443 example.com

# 25. Check for exposed git repository directory on web root
curl -I http://example.com/.git/HEAD

# 26. Verify CORS Headers Configuration
curl -I -H "Origin: http://evil.com" http://example.com/api/user

# 27. Test for Clickjacking Vulnerability (Check X-Frame-Options Header)
curl -I http://example.com | grep -i "X-Frame-Options"

# 28. Scan container images for vulnerabilities using Trivy
trivy image my_app:latest

# 29. Detect hardcoded secrets and API keys in git history (TruffleHog)
trufflehog git file://. --since-commit HEAD~10

# 30. Enforce Least Privilege Principle: Run processes under unprivileged dedicated service account
```
