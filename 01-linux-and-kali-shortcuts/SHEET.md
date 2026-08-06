# 🐧 Module 01: Linux & Kali Linux CLI Shortcut Tricks

Simple, daily-use shortcut keys and CLI tricks for Linux and Kali Linux.

---

## ⚡ 1. Terminal Keyboard Shortcuts

| Shortcut | What it Does (Simple Language) |
| :--- | :--- |
| `Ctrl + R` | Search through your command history by typing a keyword. |
| `Ctrl + C` | Instantly stop/kill the current running program. |
| `Ctrl + Z` | Pause current program and push it to background. |
| `Ctrl + L` | Clear terminal screen (same as typing `clear`). |
| `Ctrl + A` | Move cursor instantly to the START of the line. |
| `Ctrl + E` | Move cursor instantly to the END of the line. |
| `Ctrl + U` | Erase/delete everything from cursor to start of line. |
| `Ctrl + W` | Delete the single word left of the cursor. |
| `Tab` | Auto-complete file, directory, or command names. |

---

## 🪄 2. Fast Command Line Tricks

```bash
# Run previous command as sudo (saves re-typing!)
sudo !!

# Run the previous command again
!!

# Go back to previous working directory instantly
cd -

# Run command in background detached from terminal
nohup command &

# Create shortcut alias (Add to ~/.bashrc for permanence)
alias updateall="sudo apt update && sudo apt upgrade -y"
```
