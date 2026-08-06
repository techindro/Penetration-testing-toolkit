# 🔀 Module 07: Network Layer Protocols & Cookie Security Architecture

This module details ARP packet structures, Dynamic ARP Inspection (DAI) state machines, and HTTP cookie security attributes.

---

## 📐 1. Technical Concepts & Protocol Architecture

### A. Address Resolution Protocol (ARP) Header Structure
ARP maps 32-bit IPv4 addresses to 48-bit Ethernet MAC addresses.

$$\text{ARP Packet} = \Big[\text{Hardware Type (2B)}, \, \text{Protocol Type (2B)}, \, \text{Hardware Size (1B)}, \, \text{Protocol Size (1B)}, \, \text{Opcode (2B)}, \, \text{Sender MAC}, \, \text{Sender IP}, \, \text{Target MAC}, \, \text{Target IP}\Big]$$

- Opcode `1` = ARP Request (Broadcast `FF:FF:FF:FF:FF:FF`).
- Opcode `2` = ARP Reply (Unicast).

Because standard ARP lacks authentication, host ARP tables update dynamically upon receiving unrequested ARP replies (Gratuitous ARP).

### B. Cookie Security Attributes & Mitigation Matrix

| Flag | Technical Function | Security Protection |
| :--- | :--- | :--- |
| `HttpOnly` | Restricts cookie access from Client-Side JavaScript (`document.cookie`). | Mitigates XSS Session Hijacking. |
| `Secure` | Ensures cookie is transmitted strictly over TLS/HTTPS connections. | Mitigates Network Sniffing / Man-In-The-Middle. |
| `SameSite=Strict` | Prevents browser from sending cookie in cross-site requests. | Mitigates Cross-Site Request Forgery (CSRF). |

---

## 🛡️ 2. Network Hardening (Dynamic ARP Inspection - DAI)
Switches supporting DAI validate incoming ARP packets against a trusted **DHCP Snooping Binding Database**:

$$\text{DAI Decision} = \begin{cases} 
\text{Forward} & \text{if } (\text{MAC}_{\text{Packet}}, \text{IP}_{\text{Packet}}) \in \text{DHCP Binding Table} \\
\text{Drop} & \text{otherwise}
\end{cases}$$
