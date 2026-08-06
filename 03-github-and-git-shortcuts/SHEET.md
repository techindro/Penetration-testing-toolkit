# 🐙 Module 03: Git & GitHub End-to-End Command Sheet (Easy to Hard)

Complete reference for Git initialization, committing, pushing to GitHub, cloning, branch management, and advanced rebase/cherry-pick tricks with practical examples.

---

## 🟢 Level 1: Easy / Beginner Setup & Workflow (`git init` to `git push`)

### 1. Initializing a New Repository & Pushing to GitHub
```bash
# Step 1: Initialize git inside your project folder
git init

# Step 2: Configure your global user name and email
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"

# Step 3: Stage all files for commit
git add .

# Step 4: Create your first commit
git commit -m "feat: initial project commit"

# Step 5: Rename default branch to main
git branch -M main

# Step 6: Link your local repository to remote GitHub repository
git remote add origin https://github.com/username/repository.git

# Step 7: Push code to GitHub and set tracking upstream (-u)
git push -u origin main
```

### 2. Cloning & Pulling Code
```bash
# Clone an existing GitHub repository
git clone https://github.com/username/repository.git

# Pull latest changes from remote GitHub repository
git pull origin main
```

---

## 🟡 Level 2: Medium / Intermediate Branching & Stash Commands

```bash
# 1. Create and switch to a new feature branch
git checkout -b feature/login-page
# (Or using modern syntax):
git switch -c feature/login-page

# 2. View active status of modified/untracked files
git status

# 3. Temporarily stash uncommitted changes
git stash
# Restore stashed changes later:
git stash pop

# 4. View remote repository URLs
git remote -v

# 5. Fetch latest remote branch updates without merging
git fetch origin
```

---

## 🔴 Level 3: Hard / Advanced Pro Tricks & History Fixes

```bash
# 1. Display clean single-line git history graph
git log --oneline --graph --all

# 2. Undo last commit but KEEP all code changes in your workspace
git reset --soft HEAD~1

# 3. Discard ALL local uncommitted changes instantly (Revert to last clean commit)
git checkout .
# or
git restore .

# 4. Amend / Update the commit message of the most recent commit
git commit --amend -m "feat: complete user auth endpoint"

# 5. Rebase feature branch on top of main (Clean linear history)
git rebase main

# 6. Cherry-pick a specific commit from another branch into current branch
git cherry-pick <commit_hash>

# 7. GitHub Web Browser Shortcut:
# Open any GitHub repo (e.g. github.com/facebook/react), press '.' (Period key).
# Result: Launches full VS Code editor directly in your web browser!
```
