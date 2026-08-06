# 🔣 Module 16: Regex (Regular Expressions) Master Syntax & Formulas

Quick-reference regex syntax guide, character classes, lookaheads, and production-ready validation pattern formulas with practical examples.

---

## ⚡ 1. Character Classes & Metacharacters

| Token | Meaning | Practical Example |
| :--- | :--- | :--- |
| `^` | Start of string anchor. | `^http` matches strings starting with `http`. |
| `$` | End of string anchor. | `.jpg$` matches strings ending with `.jpg`. |
| `\d` | Any digit `[0-9]`. | `\d{4}` matches 4 digits (e.g. `2026`). |
| `\w` | Word character `[a-zA-Z0-9_]`. | `\w+` matches variable names. |
| `\s` | Whitespace character (space, tab, newline). | `\s+` matches one or more spaces. |
| `.+` | Any character 1 or more times. | `user=.+` matches parameter values. |
| `(?=...)` | Positive Lookahead. | `(?=.*[A-Z])` checks if string contains at least 1 uppercase letter. |

---

## 📐 2. Production Regex Validation Pattern Formulas

```regex
# 1. Email Address Validation Regex Formula
^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$
# Example Match: user.name+tag@domain.co.in

# 2. IPv4 Address Validation Regex Formula
^(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$
# Example Match: 192.168.1.254

# 3. URL Validation Regex Formula
^https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)$
# Example Match: https://github.com/techindro/Penetration-testing-toolkit
```

---

## 💻 3. Using Regex in Grep & Python

```bash
# Example 1: Grep search using extended regex (-E) for IP addresses in log
grep -E "([0-9]{1,3}\.){3}[0-9]{1,3}" access.log
```

```python
# Example 2: Python re module regex matching
import re
email = "test@domain.com"
if re.match(r"^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$", email):
    print("Valid Email!")
```
