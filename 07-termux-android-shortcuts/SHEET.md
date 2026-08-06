# 📱 Module 07: Termux Android Terminal Shortcuts & Setup

Quick-reference commands for setting up Termux on Android, storage permissions, SSH access, and package management.

---

## ⚡ 1. Initial Setup & Storage Permission

```bash
# Update Termux core package repositories
pkg update && pkg upgrade -y

# Grant storage access permission (Access phone SD Card / Internal storage)
termux-setup-storage

# Access internal storage folder:
cd ~/storage/shared
```

---

## 🛠️ 2. Essential Termux Tools Installation

```bash
# Install Python, Git, Curl, and OpenSSH on Termux
pkg install python git openjdk-17 openssh curl wget -y

# Start SSH server on phone (connect from PC terminal)
sshd
# Check username:
whoami
# Check phone IP address:
ifconfig
# Connect from PC: ssh username@phone_ip -p 8022
```

---

## 🔋 3. Battery Optimization & Background Execution

```bash
# Acquire Wakelock (Prevents Android from killing Termux when app is in background)
termux-wake-lock

# Release Wakelock
termux-wake-unlock
```
