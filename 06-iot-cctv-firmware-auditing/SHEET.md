# 🎥 Module 06: IoT & CCTV Firmware Security Auditing

This module covers embedded Linux file system analysis, magic byte signatures, RTSP protocol mechanics, and static binary analysis.

---

## 📐 1. Technical Concepts & Architecture

### A. Binary File Magic Bytes & Headers
Firmware images are composite binary blobs containing bootloaders (U-Boot), Linux kernel images (uImage/zImage), and compressed file systems (SquashFS, CramFS, JFFS2).

| Filesystem / Format | Magic Byte Signature (Hex) | ASCII representation |
| :--- | :--- | :--- |
| **SquashFS** | `0x68 0x73 0x71 0x73` / `0x73 0x71 0x73 0x68` | `hsqs` / `sqsh` |
| **GZIP** | `0x1F 0x8B 0x08` | N/A |
| **U-Boot Image** | `0x27 0x05 0x19 0x56` | Image Header |

### B. Binwalk Signature Extraction Mechanics
Binwalk scans raw binary streams byte-by-byte using regex signature tables to locate embedded headers, calculating block offsets and extracting filesystem archives automatically.

---

## 🛠️ 2. Core Tool Breakdown (Binwalk & Nmap)

```bash
binwalk -e --rm firmware.bin
```
- `-e` / `--extract` : Automatically extract known file types and compressed filesystems.
- `--rm` : Clean up temporary extracted archives after unpacking.

```bash
nmap -p 554,80,8080 -sV --script rtsp-url-brute <target-ip>
```
- `-p <ports>` : Audit specific RTSP (554) and HTTP management ports.
- `-sV` : Probe open ports to determine service name and version info.
- `--script <nse>` : Run Nmap Script Engine (NSE) script to discover media streaming paths.

---

## 🛡️ 3. Embedded System Hardening
- **Cryptographic Boot (Secure Boot):** Enforce hardware Root of Trust (RoT) to verify digital signatures on firmware updates before flashing.
- **Credential Storage:** Store authentication hashes in hardware Secure Element / TPM instead of plain text configuration files.
