# 🛡️ Module 14: Security Auditing & Network Diagnostics Shortcuts

Essential command line shortcuts with practical usage examples for network diagnostics, packet capturing, port scanning, and security verification.

---

## 🎯 1. Nmap Port Scanning & Host Discovery

```bash
# Example 1: Fast SYN Stealth Scan on top 1000 ports with service version detection
nmap -sS -sV -O 192.168.1.50
# Usage: Detects open ports, running service names, versions, and operating system.

# Example 2: Target specific ports with default security scripts (-sC)
nmap -p 22,80,443 -sC -sV 192.168.1.50
# Usage: Executes light NSE security scripts against HTTP/SSH ports.

# Example 3: Subnet Ping Sweep (Host Discovery)
nmap -sn 192.168.1.0/24
# Output: Returns list of all online IP addresses on local network.
```

---

## 📡 2. Packet Capture & Traffic Inspection (`tcpdump` & `tshark`)

```bash
# Example 1: Capture packets on interface eth0 and filter HTTP traffic (Port 80)
sudo tcpdump -i eth0 port 80 -n -X
# Usage: Displays raw packet headers and ASCII payload data on terminal.

# Example 2: Save packet capture to .pcap file for Wireshark analysis
sudo tcpdump -i wlan0 -w network_traffic.pcap

# Example 3: Read and extract HTTP Host headers using TShark
tshark -r network_traffic.pcap -Y "http.request" -T fields -e http.host -e http.request.uri
```

---

## 🔌 3. Network Connection & Netcat Checks (`nc` & `socat`)

```bash
# Example 1: Check raw TCP port connectivity to host
nc -zv 192.168.1.50 80
# Output: Connection to 192.168.1.50 80 port [tcp/http] succeeded!

# Example 2: Listen on local TCP port 4444 (Netcat Listener)
nc -l -p 4444
```
