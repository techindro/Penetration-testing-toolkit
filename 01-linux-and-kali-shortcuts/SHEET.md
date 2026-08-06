# 🐧 Module 01: Linux & Kali Linux CLI Shortcuts (Easy to Hard)

Complete command shortcuts with practical examples categorized by difficulty level (🟢 Easy, 🟡 Medium, 🔴 Hard).

---

## 🟢 Level 1: Easy / Beginner Commands

```bash
# 1. Clear terminal screen
Ctrl + L

# 2. Return to user home directory
cd ~

# 3. Print current working directory path
pwd

# 4. List files with permissions and hidden files
ls -la
```

---

## 🟡 Level 2: Medium / Intermediate Commands

```bash
# 1. Search interactive command history
Ctrl + R
# Example: Type 'ssh' to find your last remote connection command.

# 2. Return to previous working directory instantly
cd -

# 3. View real-time output of growing log file
tail -f /var/log/syslog

# 4. Search for process PID by name
pgrep -l node
```

---

## 🔴 Level 3: Hard / Advanced Pro Tricks

```bash
# 1. Run previous command as root without retyping
sudo !!

# 2. Detach process and run in background permanently
nohup python3 server.py > server.log 2>&1 &

# 3. Force kill all processes matching name pattern
pkill -9 -f node

# 4. Create custom permanent alias
alias updateall="sudo apt update && sudo apt upgrade -y"
```
