# 🐧 Module 01: Linux & Kali Linux Comprehensive CLI Shortcuts

Complete, practical command shortcuts and daily tricks for Linux and Kali Linux administration, terminal navigation, and process management.

---

## ⚡ 1. Daily Terminal Navigation Shortcuts

| Key Combination | Simple Explanation (What it does) |
| :--- | :--- |
| `Ctrl + R` | Search command history interactively by typing any matching keyword. |
| `Ctrl + C` | Instantly stop/terminate the currently executing program or process. |
| `Ctrl + Z` | Suspend current process and move it to the background. |
| `Ctrl + L` | Clear terminal screen instantly (same as typing `clear`). |
| `Ctrl + A` | Move cursor directly to the beginning of the command line. |
| `Ctrl + E` | Move cursor directly to the end of the command line. |
| `Ctrl + U` | Clear the entire line from cursor position back to the start. |
| `Ctrl + W` | Delete the single word immediately before the cursor. |
| `Ctrl + Y` | Paste (yank) the text previously cleared by `Ctrl+U` or `Ctrl+W`. |
| `Tab` | Auto-complete command names, file paths, and directories. |

---

## 🪄 2. Time-Saving CLI Tricks

```bash
# Execute the previous command as root (sudo) without retyping
sudo !!

# Execute the previous command exactly as it was run
!!

# Return immediately to the previous working directory
cd -

# Return directly to the logged-in user's home directory
cd ~

# Run a long command in background detached from terminal output
nohup command > output.log 2>&1 &

# View real-time output of a growing log file
tail -f /var/log/syslog

# Search for a running process PID quickly
pgrep -l process_name

# Force kill all processes matching a specific name
pkill -9 -f process_name

# Create a permanent custom alias (Add to ~/.bashrc or ~/.zshrc)
alias updateall="sudo apt update && sudo apt upgrade -y"
alias ports="sudo ss -tulpn"
```
