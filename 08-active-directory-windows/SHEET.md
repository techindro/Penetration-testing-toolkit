# 🏰 Module 08: Active Directory Security & Cryptographic Hashes

This module covers NTLMv2 hash computation formulas, LLMNR/NBT-NS protocol mechanics, Hashcat modes, and Active Directory hardening.

---

## 📐 1. Technical Concepts & Mathematical Models

### A. NTLMv2 Hash Cryptographic Formula
The NTLMv2 hash response is computed dynamically using HMAC-MD5 over user identities and server challenges:

#### Step 1: NTLM Hash
$$\text{NTLM Hash} = \text{MD4}\big(\text{UTF16LE}(\text{Password})\big)$$

#### Step 2: NTLMv2 Response Computation
$$\text{NTLMv2 Hash} = \text{HMAC-MD5}\Big(\text{NTLM Hash}, \; \text{Uppercase}(\text{Username}) \mathbin{\Vert} \text{UserDomain}\Big)$$

$$\text{NTLMv2 Response} = \text{HMAC-MD5}\Big(\text{NTLMv2 Hash}, \; \text{ServerChallenge} \mathbin{\Vert} \text{ClientBlob}\Big)$$

### B. LLMNR / NBT-NS Poisoning Concepts
When a Windows machine fails to resolve a hostname via DNS, it falls back to link-local multicast broadcasts (**LLMNR** on UDP 5355, **NBT-NS** on UDP 137).

---

## 🛠️ 2. Core Tool Breakdown (Hashcat)

Hashcat is an advanced password recovery utility supporting GPU hardware acceleration.

```bash
hashcat -m 5600 ntlmv2_hashes.txt /usr/share/wordlists/rockyou.txt -r /usr/share/hashcat/rules/best64.rule
```

### Parameter Breakdown:
- `-m 5600` : Specify hash type mode (`5600` = NetNTLMv2 / NTLMv2).
- `-r <rule>` : Apply mutation rules (append numbers, uppercase letters, substitute characters) to each base wordlist entry.

---

## 🛡️ 3. Active Directory Hardening Checklist
1. **Disable LLMNR/NBT-NS:** Enforce via Group Policy Object (GPO):
   `Computer Configuration -> Administrative Templates -> Network -> DNS Client -> Turn off multicast name resolution = Enabled`
2. **SMB Signing:** Enforce `Digitally sign communications (always)` on all domain controllers and member servers.
