# 📡 Module 03: Linux Networking, Ports & Firewall Commands

Quick-reference cheat-sheet for network interface configuration, listening port inspection, curl/wget API testing, and firewall rule management.

---

## 🌐 1. IP & Interface Configuration (`ip`, `ifconfig`, `dig`)

```bash
# View IP addresses assigned to network interfaces
ip a

# View network routing table
ip route

# Query DNS records for a domain (A, CNAME, MX)
dig target.com ANY +short

# Reverse DNS lookup (IP to domain)
dig -x 192.168.1.1
```

---

## 🔌 2. Listening Ports & Sockets (`ss` & `netstat`)

```bash
# Display all listening TCP (-t) & UDP (-u) ports with Process IDs (-p) and Numeric format (-n)
ss -tulpn

# Filter listening ports on port 80 or 443
ss -tulpn | grep -E ':80|:443'

# Test raw TCP connection to host and port (Netcat)
nc -zv 192.168.1.50 80
```

---

## 🌐 3. Web Requests & API Testing (`curl` & `wget`)

```bash
# Fetch web page headers only (-I)
curl -I https://target.com

# Send HTTP POST request with JSON data and custom headers
curl -X POST https://api.target.com/login \
     -H "Content-Type: application/json" \
     -d '{"user":"admin","pass":"secret"}'

# Download file with resume capability (-c)
wget -c https://example.com/file.zip -O output.zip
```

---

## 🧱 4. Firewall Rule Management (`ufw` & `iptables`)

```bash
# View Uncomplicated Firewall (UFW) status
sudo ufw status verbose

# Allow port 22 (SSH) and 80 (HTTP)
sudo ufw allow 22/tcp
sudo ufw allow 80/tcp

# Enable UFW firewall
sudo ufw enable
```
