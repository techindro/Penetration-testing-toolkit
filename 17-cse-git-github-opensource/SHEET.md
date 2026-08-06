# 🐙 Module 17: Git, GitHub Open-Source & Contribution Playbook

Complete guide to Git commands, handling merge conflicts, SSH key authentication, creating Pull Requests (PR), and contributing to open-source software projects.

---

## 🔑 1. Setting Up SSH Authentication with GitHub

```bash
# 1. Generate SSH Key (ED25519 algorithm)
ssh-keygen -t ed25519 -C "your_email@example.com"

# 2. Start SSH Agent and Add Key
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# 3. Copy Public Key to Clipboard and add to GitHub Settings -> SSH Keys
cat ~/.ssh/id_ed25519.pub

# 4. Test SSH Connection
ssh -T git@github.com
```

---

## 🔀 2. Resolving Git Merge Conflicts

```bash
# Fetch latest upstream changes
git fetch origin

# Rebase feature branch on main
git rebase origin/main

# If conflicts occur:
# 1. Open conflicted files and resolve <<<<<<< HEAD markers
# 2. Stage resolved files:
git add .
# 3. Continue rebase:
git rebase --continue
```

---

## 🚀 3. Open-Source Pull Request (PR) Workflow

```bash
# 1. Fork repository on GitHub, then clone your fork:
git clone https://github.com/YOUR_USERNAME/open-source-repo.git
cd open-source-repo

# 2. Add original upstream repository as remote:
git remote add upstream https://github.com/ORIGINAL_OWNER/open-source-repo.git

# 3. Create new feature branch:
git checkout -b feature/add-new-feature

# 4. Make changes, commit, and push to your fork:
git add .
git commit -m "feat: implement new security auditing feature"
git push origin feature/add-new-feature

# 5. Open GitHub and click "Compare & pull request"!
```
