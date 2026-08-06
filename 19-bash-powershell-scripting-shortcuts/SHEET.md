# 📜 Module 19: Bash & PowerShell Scripting One-Liners

Quick-reference command one-liners for automation, loops, environment variables, cron scheduling, and PowerShell administrative tasks with practical examples.

---

## 🐚 1. Bash Shell One-Liners & Automation Examples

```bash
# Example 1: Loop over a list of domains or IP addresses in bash
for ip in 192.168.1.1 192.168.1.2 192.168.1.3; do ping -c 1 $ip; done

# Example 2: Export temporary environment variable for current terminal session
export DATABASE_URL="postgres://user:pass@localhost:5432/appdb"

# Example 3: Schedule cron job (Open interactive crontab editor)
crontab -e
# Add line to run backup script daily at 2:00 AM:
# 0 2 * * * /bin/bash /home/user/scripts/backup.sh > /dev/null 2>&1

# Example 4: Read file line-by-line in bash loop
while IFS= read -r line; do echo "Processing: $line"; done < targets.txt
```

---

## ⚡ 2. Windows PowerShell One-Liners & Examples

```powershell
# Example 1: Search for text inside files recursively (Select-String)
Select-String -Path "C:\Project\*.js" -Pattern "API_KEY"

# Example 2: List files recursively filtering by extension (.log)
Get-ChildItem -Path "C:\var\logs\" -Filter "*.log" -Recurse

# Example 3: Set environment variable in PowerShell session
$env:PORT = "3000"

# Example 4: Test network port connection (PowerShell ping/nc alternative)
Test-NetConnection -ComputerName "localhost" -Port 80
# Output: TcpTestSucceeded : True
```
