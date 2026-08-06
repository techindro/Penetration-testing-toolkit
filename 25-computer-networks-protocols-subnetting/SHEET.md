# 🌐 Module 25: Computer Networks (CN), Standard Ports & Subnetting

Quick-reference cheat-sheet for the OSI model layers, TCP 3-way handshake, well-known port numbers, HTTP status codes, and IP subnetting formulas.

---

## 📡 1. The 7 Layers of the OSI Model

| Layer Number | Layer Name | Protocol Data Unit (PDU) | Protocols / Standards |
| :-: | :--- | :--- | :--- |
| **7** | **Application** | Data | HTTP, HTTPS, FTP, SSH, DNS, SMTP |
| **6** | **Presentation** | Data | TLS, SSL, JPEG, ASCII, Encryption |
| **5** | **Session** | Data | NetBIOS, PPTP, RPC, Sockets |
| **4** | **Transport** | Segment (TCP) / Datagram (UDP) | TCP, UDP |
| **3** | **Network** | Packet | IP (IPv4/IPv6), ICMP, ARP, BGP |
| **2** | **Data Link** | Frame | Ethernet, Wi-Fi (802.11), MAC Address |
| **1** | **Physical** | Bit | Cables, Fiber, Hubs, Signal Repeaters |

---

## 🔌 2. Well-Known Service Ports (Must-Know for CSE Exams & Labs)

| Port Number | Protocol / Service | Description |
| :-: | :--- | :--- |
| `20 / 21` | **FTP** | File Transfer Protocol |
| `22` | **SSH / SFTP** | Secure Shell Remote Login |
| `23` | **Telnet** | Unencrypted Remote Terminal |
| `25` | **SMTP** | Simple Mail Transfer Protocol |
| `53` | **DNS** | Domain Name System |
| `80` | **HTTP** | Unencrypted Web Traffic |
| `443` | **HTTPS** | Encrypted TLS/SSL Web Traffic |
| `3306` | **MySQL** | MySQL Database Connection |
| `5432` | **PostgreSQL** | PostgreSQL Database Connection |
| `27017` | **MongoDB** | MongoDB NoSQL Connection |

---

## 🔢 3. HTTP Status Codes Cheat Sheet

- **`200 OK`**: Request succeeded.
- **`201 Created`**: Resource successfully created.
- **`301 Moved Permanently`**: Permanent URL redirect.
- **`400 Bad Request`**: Client-side syntax error.
- **`401 Unauthorized`**: Authentication credentials missing.
- **`403 Forbidden`**: Authenticated but lacks required permissions.
- **`404 Not Found`**: Target endpoint does not exist.
- **`500 Internal Server Error`**: Backend application crashed.
- **`502 Bad Gateway`**: Upstream server failed (e.g., Nginx -> Node.js down).
- **`503 Service Unavailable`**: Server overloaded or under maintenance.

---

## 🧮 4. IPv4 Subnetting Formulas

$$\text{Usable Hosts per Subnet} = 2^{(32 - \text{CIDR Prefix})} - 2$$

- **`/24 Subnet`**: $2^{(32-24)} - 2 = 256 - 2 = 254$ Usable Hosts (Subnet Mask: `255.255.255.0`).
- **`/16 Subnet`**: $2^{(32-16)} - 2 = 65,536 - 2 = 65,534$ Usable Hosts (Subnet Mask: `255.255.0.0`).
