# 🐙 Module 03: Git & GitHub Shortcut Tricks

One-liner Git commands for fast committing, stashing changes, fixing mistakes, and clean log viewing.

---

## ⚡ 1. Git One-Liner Shortcuts

```bash
# Pretty git history graph in one line
git log --oneline --graph --all

# Temporarily save uncommitted work and revert later
git stash
git stash pop

# Undo last commit but keep your code changes in working folder
git reset --soft HEAD~1

# Discard ALL uncommitted local changes instantly
git checkout .
# or
git restore .

# Change commit message of the last commit
git commit --amend -m "new updated commit message"
```

---

## 🚀 2. GitHub CLI & Web Shortcuts

```bash
# Clone repository quickly via SSH
git clone git@github.com:username/repository.git

# Fast SSH connection test
ssh -T git@github.com

# GitHub Web Shortcut:
# Press '.' (Period key) while viewing any repository on GitHub.com to open VS Code Web directly in browser!
```
