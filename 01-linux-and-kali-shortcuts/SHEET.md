# 🐧 Module 01: Linux & Kali Linux CLI Master Sheet (30+ Commands)

Complete reference for 30+ essential Linux & Kali Linux command shortcuts with practical usage examples categorized by difficulty level (🟢 Easy, 🟡 Medium, 🔴 Hard).

---

## 🟢 Level 1: Easy / Beginner Commands (1 - 10)

```bash
# 1. Clear terminal screen
Ctrl + L

# 2. Return to current user home directory
cd ~

# 3. Print absolute path of current working directory
pwd

# 4. List files with detailed permissions, file size, and hidden files
ls -la

# 5. Create a new directory
mkdir -p my_project/src

# 6. Create an empty file or update timestamp
touch index.js

# 7. Copy file to target location
cp config.json config.json.bak

# 8. Move or rename file
mv old_name.txt new_name.txt

# 9. View file content in terminal
cat README.md

# 10. Display current system hostname
hostname
```

---

## 🟡 Level 2: Medium / Intermediate Commands (11 - 20)

```bash
# 11. Interactive command history search
Ctrl + R

# 12. Return to previous working directory instantly
cd -

# 13. View real-time output of growing log file
tail -f /var/log/syslog

# 14. Search for process PID by process name
pgrep -l node

# 15. Search for text pattern recursively inside directory files
grep -rnw './src' -e 'API_KEY'

# 16. Change file permissions (Read, Write, Execute for Owner)
chmod 755 script.sh

# 17. Change file owner and group
sudo chown user:www-data /var/www/html -R

# 18. Display RAM memory usage in human-readable format (MB/GB)
free -h

# 19. Display disk space utilization on mounted filesystems
df -h

# 20. Archive and compress directory into tar.gz
tar -czvf backup.tar.gz /var/www/html
```

---

## 🔴 Level 3: Hard / Advanced Pro Tricks (21 - 32)

```bash
# 21. Re-run previous command as root without retyping
sudo !!

# 22. Detach process and run in background permanently (survives SSH disconnect)
nohup python3 server.py > server.log 2>&1 &

# 23. Force kill all processes matching name pattern
pkill -9 -f node

# 24. Find files larger than 100MB in system
find /var -type f -size +100M -exec ls -lh {} \;

# 25. Monitor active network connections and listening ports
sudo netstat -tulpn

# 26. Display interactive process monitor sorted by CPU/Memory (htop)
htop

# 27. Create custom permanent alias in ~/.bashrc
alias updateall="sudo apt update && sudo apt upgrade -y"

# 28. Extract compressed tar.gz archive
tar -xzvf archive.tar.gz

# 29. Synchronize files to remote server via SSH (rsync)
rsync -avz -e ssh ./dist/ user@remote_ip:/var/www/app/

# 30. Check active listening TCP ports using ss
ss -tulpn

# 31. Monitor system disk I/O performance
iostat -xz 1 10

# 32. View system kernel boot logs (dmesg)
dmesg -T | tail -n 20
```
