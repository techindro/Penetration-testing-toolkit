# 📱 Module 11: Termux Android Terminal Shortcuts & Setup Examples

Quick-reference commands with practical examples for setting up Termux on Android, storage permissions, SSH access, and package management.

---

## ⚡ 1. Initial Setup & Storage Examples

```bash
# Example 1: Update Termux core package repositories
pkg update && pkg upgrade -y

# Example 2: Grant storage access permission (Access phone SD Card / Internal storage)
termux-setup-storage
# Usage: Pops up Android storage permission dialog. Accept it to unlock ~/storage folder!

# Example 3: Access internal storage / Downloads folder:
cd ~/storage/shared/Download
# Usage: Allows you to view and process files downloaded on your phone.
```

---

## 🛠️ 2. Essential Termux Tools & SSH Server Examples

```bash
# Example 1: Install Python, Git, Curl, and OpenSSH on Termux
pkg install python git openjdk-17 openssh curl wget -y

# Example 2: Start OpenSSH server on phone
sshd
# Check phone username:
whoami
# Check phone IP address:
ifconfig

# Example 3: Connect from your PC terminal to your phone terminal!
ssh u0_a245@192.168.1.15 -p 8022
# Result: Control your Android Termux terminal directly from your laptop screen!
```

---

## 🔋 3. Battery Optimization Example

```bash
# Example 1: Acquire Wakelock (Prevents Android from killing Termux in background)
termux-wake-lock
# Usage: Run before executing long python scripts or servers on your phone!

# Example 2: Release Wakelock when finished
termux-wake-unlock
```
