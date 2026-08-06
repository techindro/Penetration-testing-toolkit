# 🌐 Module 25: Computer Networks (CN), Standard Ports & Subnetting

> [!TIP]
> 🧠 **OSI 7 Layers Mnemonic (Top to Bottom):**
> **A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing
> - **A**pplication (Layer 7)
> - **P**resentation (Layer 6)
> - **S**ession (Layer 5)
> - **T**ransport (Layer 4)
> - **N**etwork (Layer 3)
> - **D**ata Link (Layer 2)
> - **P**hysical (Layer 1)

---

## 📡 1. The 7 Layers of the OSI Model

| Layer Number | Layer Name | Protocol Data Unit (PDU) | Protocols / Standards | Memory Hook |
| :-: | :--- | :--- | :--- | :--- |
| **7** | **Application** | Data | HTTP, HTTPS, SSH, DNS | What the user interacts with (Browsers, Apps) |
| **6** | **Presentation** | Data | TLS, SSL, JPEG, Encryption | Data Formatting & Encryption |
| **5** | **Session** | Data | NetBIOS, Sockets, RPC | Establishes & maintains connections |
| **4** | **Transport** | Segment (TCP) / Datagram (UDP) | TCP, UDP | End-to-End Reliability (Ports) |
| **3** | **Network** | Packet | IP (IPv4/v6), ICMP, ARP | Logical Addressing & Routing (IP Address) |
| **2** | **Data Link** | Frame | Ethernet, Wi-Fi, MAC Address | Physical Hardware Addressing (MAC Address) |
| **1** | **Physical** | Bit | Cables, Fiber, Signals | Binary $0$s and $1$s over wire/air |

---

## 🔌 2. Well-Known Service Ports (Must-Know for CSE Exams & Labs)

| Port Number | Protocol / Service | Memory Hook | Description |
| :-: | :--- | :--- | :--- |
| `20 / 21` | **FTP** | **F**ile **T**ransfer | File Transfer Protocol |
| `22` | **SSH / SFTP** | **S**ecure **S**hell | Encrypted Remote Terminal Login |
| `23` | **Telnet** | Unencrypted Remote | Plaintext Remote Terminal |
| `25` | **SMTP** | **S**end **M**ail | Simple Mail Transfer Protocol |
| `53` | **DNS** | Domain Name | Domain Name System (IP Resolver) |
| `80` | **HTTP** | Web Unencrypted | Standard Web Traffic |
| `443` | **HTTPS** | Web Encrypted (SSL) | Secure TLS Web Traffic |
| `3306` | **MySQL** | DB SQL | MySQL Database Connection |
| `5432` | **PostgreSQL** | DB Postgres | PostgreSQL Database Connection |
| `27017` | **MongoDB** | DB NoSQL | MongoDB NoSQL Connection |

---

## 🔢 3. HTTP Status Codes Memory Hooks

- **`2xx` = Success!** (`200 OK` = Works, `201 Created` = Resource created).
- **`3xx` = Redirection!** (`301 Moved Permanently` = Go to new URL).
- **`4xx` = You (Client) Made a Mistake!** (`400 Bad Request`, `401 Unauthorized`, `403 Forbidden`, `404 Not Found`).
- **`5xx` = Server (Backend) Crashed!** (`500 Internal Error`, `502 Bad Gateway`, `503 Service Unavailable`).

---

## 🧮 4. IPv4 Subnetting Formulas

$$\text{Usable Hosts per Subnet} = 2^{(32 - \text{CIDR Prefix})} - 2$$

- **`/24 Subnet`**: $2^{(32-24)} - 2 = 256 - 2 = 254$ Usable Hosts (Subnet Mask: `255.255.255.0`).
- **`/16 Subnet`**: $2^{(32-16)} - 2 = 65,536 - 2 = 65,534$ Usable Hosts (Subnet Mask: `255.255.0.0`).
