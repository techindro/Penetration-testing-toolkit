# ⚡ Module 04: Process Management, Systemd & Resource Commands

Quick-reference cheat-sheet for running background processes, managing services (`systemctl`), reading service logs (`journalctl`), and killing hung processes.

---

## ⚙️ 1. Process Inspection & Management (`ps`, `top`, `htop`)

```bash
# View all running processes with user details
ps aux

# Search for process PID by name
pgrep -l nginx

# Kill process by Process ID (PID)
kill -9 <PID>

# Kill all processes matching process name
killall -9 node
pkill -f python
```

---

## 🛠️ 2. Systemd Service Control (`systemctl`)

```bash
# View service status
sudo systemctl status nginx

# Start / Stop / Restart service
sudo systemctl start postgresql
sudo systemctl stop apache2
sudo systemctl restart docker

# Enable service to start automatically on system boot
sudo systemctl enable docker

# Disable service on boot
sudo systemctl disable apache2
```

---

## 📜 3. Inspection of System Logs (`journalctl`)

```bash
# View real-time tail logs for a specific service (-u)
sudo journalctl -u nginx -f

# View logs generated since current system boot (-b)
sudo journalctl -b

# Filter logs by priority level (err, warning, info)
sudo journalctl -u docker -p err
```

---

## 💻 4. Resource & Memory Monitoring (`free`, `uptime`, `nohup`)

```bash
# View RAM and Swap usage in Megabytes / Gigabytes
free -h

# View CPU load average and system uptime
uptime

# Run process in background detached from terminal (nohup)
nohup python3 server.py > server.log 2>&1 &
```
