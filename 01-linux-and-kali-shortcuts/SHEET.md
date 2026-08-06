# 🐧 Module 01: Linux & Kali Linux Comprehensive CLI Shortcuts

Complete command shortcuts with practical examples for Linux and Kali Linux administration, terminal navigation, and process management.

---

## ⚡ 1. Daily Terminal Keyboard Shortcuts

| Key Combination | Action (What it does) | Practical Usage Example |
| :--- | :--- | :--- |
| `Ctrl + R` | Search command history interactively. | Type `Ctrl+R` then `ssh` to quickly find your last `ssh user@192.168.1.5` command. |
| `Ctrl + C` | Instantly stop/kill the current running program. | Press `Ctrl+C` when `ping google.com` or a script is running infinitely. |
| `Ctrl + Z` | Suspend current process to background. | Press `Ctrl+Z` while editing in `nano`, then type `fg` to resume editing later. |
| `Ctrl + L` | Clear terminal screen. | Press `Ctrl+L` instead of typing `clear` to get a fresh clean prompt. |
| `Ctrl + A` | Move cursor to the beginning of the line. | Jump to start of `sudo apt update` to change `sudo` to `echo`. |
| `Ctrl + E` | Move cursor to the end of the line. | Jump to end of long command to append `| grep error`. |
| `Ctrl + U` | Erase line from cursor back to start. | Erase mistyped secret password or long command line instantly. |
| `Ctrl + W` | Delete word before cursor. | Delete mistyped directory name at the end of `cd /var/www/html/old_folder`. |
| `Tab` | Auto-complete files & commands. | Type `cd /v` and hit `Tab` to auto-complete to `cd /var/`. |

---

## 🪄 2. Fast Command Line Examples

```bash
# Example 1: Run previous command as root (sudo) without retyping
# If you ran: apt update (Permission denied)
sudo !!
# Output: Runs 'sudo apt update' automatically.

# Example 2: Return to previous working directory instantly
cd /var/www/html/app/
cd /etc/nginx/
cd -
# Output: Switched back to /var/www/html/app/

# Example 3: Run command in background detached from terminal output
nohup python3 server.py > server.log 2>&1 &
# Output: Server runs in background even if you close the terminal.

# Example 4: View real-time output of a growing log file
tail -f /var/log/syslog
# Output: Continuously streams new system log entries as they happen.

# Example 5: Search for a running process PID quickly
pgrep -l node
# Output: 14520 node

# Example 6: Force kill all processes matching a specific name
pkill -9 -f node
# Output: Terminates all running node processes instantly.

# Example 7: Create permanent custom shortcuts (Aliases)
alias updateall="sudo apt update && sudo apt upgrade -y"
alias ports="sudo ss -tulpn"
# Usage: Simply type 'updateall' or 'ports' in terminal.
```
