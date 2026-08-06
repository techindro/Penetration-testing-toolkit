# 🐙 Module 03: Git & GitHub Comprehensive One-Liners & Tricks

Essential Git one-liners and GitHub workflow tricks for committing, branch management, fixing mistakes, and clean history visualization.

---

## ⚡ 1. Git Daily One-Liners

```bash
# Display clean single-line git history with branch graph
git log --oneline --graph --all

# Save uncommitted changes temporarily without committing
git stash
# Restore previously stashed changes
git stash pop

# Undo the most recent commit while keeping all code changes in workspace
git reset --soft HEAD~1

# Discard all local uncommitted changes instantly (Fresh start)
git checkout .
# or
git restore .

# Update the message of the last commit
git commit --amend -m "Updated commit message"

# Rename local branch
git branch -m old-name new-name

# Delete local branch
git branch -d branch-name

# Delete remote branch on GitHub
git push origin --delete branch-name

# Clean untracked files and directories from repository
git clean -fd
```

---

## 🚀 2. GitHub Web & CLI Shortcuts

```bash
# Clone repository using SSH key
git clone git@github.com:username/repository.git

# Test GitHub SSH connection
ssh -T git@github.com

# GitHub Web Browser Shortcut:
# Press '.' (Period key) while viewing any repository on GitHub.com to open web-based VS Code directly in your browser!
```
