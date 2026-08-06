# 📡 Module 05: Wireless Security & Cryptographic Handshakes

This notebook section covers 802.11 wireless frame structures, WPA2 4-Way Handshake cryptography, key derivation functions (PBKDF2), and tool specifications.

---

## 📐 1. Technical Concepts & Mathematical Models

### A. WPA2 4-Way Handshake Exchange Diagram

```mermaid
sequenceDiagram
    autonumber
    participant AP as Access Point (Authenticator)
    participant Supplicant as Wireless Client (Supplicant)
    
    Note over AP,Supplicant: Both AP and Client possess PMK = PBKDF2(Passphrase, SSID, 4096, 256)
    
    AP->>Supplicant: 1. EAPOL-Key (ANonce)
    Note over Supplicant: Supplicant derives PTK using ANonce + SNonce + MACs
    Supplicant->>AP: 2. EAPOL-Key (SNonce + MIC)
    Note over AP: AP derives PTK & verifies MIC
    AP->>Supplicant: 3. EAPOL-Key (GTK + MIC)
    Supplicant->>AP: 4. EAPOL-Key (ACK)
    
    Note over AP,Supplicant: 4-Way Handshake Complete. Encrypted Session Active.
```

### B. Pairwise Master Key (PMK) Derivation Math
The PMK is computed using the WPA passphrase and Network SSID via **PBKDF2** (Password-Based Key Derivation Function 2) with 4096 HMAC-SHA1 iterations:

$$\text{PMK} = \text{PBKDF2-HMAC-SHA1}\big(\text{Passphrase}, \; \text{SSID}, \; 4096, \; 256\big)$$

---

## 🛠️ 2. Core Tool Breakdown (Aircrack-ng Suite)

```bash
airodump-ng -c 6 --bssid 00:11:22:33:44:55 -w capture_output wlan0mon
```

### Parameter Breakdown:
- `-c <channel>` : Lock wireless interface to specific 802.11 RF channel (e.g. Channel 6).
- `--bssid <MAC>` : Filter capture strictly to target Access Point BSSID MAC address.
- `-w <prefix>` : Write captured packet frames to file (`capture_output-01.cap`).
