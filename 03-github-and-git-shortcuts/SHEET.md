# 🐙 Module 03: Git & GitHub Master Command Sheet (30 Commands)

> [!TIP]
> 🧠 **Memory Hook:** Think of Git like taking photo snapshots of your code!
> - `git add` = Framing the camera shot (Staging area).
> - `git commit` = Clicking the photo shutter (Local memory save).
> - `git push` = Uploading the photo to Instagram (Remote GitHub server).

---

## 🟢 Level 1: Easy / Beginner Commands (1 - 10)

```bash
# 1. Initialize new local git repository
# 💡 Memory Hook: Starts a blank new photo album
git init

# 2. Configure global user name
git config --global user.name "Shubham Patel"

# 3. Configure global user email
git config --global user.email "techindro@example.com"

# 4. Stage all modified and new files for commit
# 💡 Memory Hook: Adds all modified files to the photo frame
git add .

# 5. Commit staged changes with message
# 💡 Memory Hook: Takes the permanent local snapshot
git commit -m "feat: initial commit"

# 6. Check status of working directory and staging area
# 💡 Memory Hook: Shows which files changed since last snapshot
git status

# 7. Rename current branch to main
git branch -M main

# 8. Add remote GitHub repository URL
# 💡 Memory Hook: Connects local album to GitHub cloud link
git remote add origin https://github.com/techindro/repository.git

# 9. Push commits to remote branch and set upstream (-u)
# 💡 Memory Hook: Uploads local snapshots to GitHub server
git push -u origin main

# 10. Clone remote GitHub repository to local machine
# 💡 Memory Hook: Downloads entire project folder from GitHub
git clone https://github.com/techindro/repository.git
```

---

## 🟡 Level 2: Medium / Intermediate Commands (11 - 20)

```bash
# 11. Pull latest commits from remote main branch
# 💡 Memory Hook: Downloads & merges latest team code updates
git pull origin main

# 12. Create and switch to new feature branch
# 💡 Memory Hook: Creates parallel safe sandbox workspace
git checkout -b feature/user-auth

# 13. List all local and remote branches
git branch -a

# 14. Switch to existing branch
git switch main

# 15. Merge feature branch into current branch
# 💡 Memory Hook: Joins feature branch work back into main code
git merge feature/user-auth

# 16. Temporarily stash uncommitted changes
# 💡 Memory Hook: Hides uncommitted work in secret drawer
git stash

# 17. Restore most recently stashed changes
# 💡 Memory Hook: Pulls work back out of secret drawer
git stash pop

# 18. List all stashed change sets
git stash list

# 19. View remote repository URLs
git remote -v

# 20. Fetch updates from remote without merging
git fetch origin
```

---

## 🔴 Level 3: Hard / Advanced Pro Tricks (21 - 30)

```bash
# 21. Single-line graphical commit history graph
# 💡 Memory Hook: Visual tree map of all project commits
git log --oneline --graph --all

# 22. Undo last commit but keep changes in workspace (Soft Reset)
# 💡 Memory Hook: Undoes commit button press without losing code
git reset --soft HEAD~1

# 23. Undo last commit and discard all changes (Hard Reset - Danger!)
# 💡 Memory Hook: Emergency wipeout back to last clean commit
git reset --hard HEAD~1

# 24. Discard all uncommitted local modifications in workspace
# 💡 Memory Hook: Reverts workspace back to last commit state
git checkout .

# 25. Amend most recent commit message or add forgotten files
git commit --amend -m "feat: complete login authentication API"

# 26. Rebase feature branch onto main (Clean linear history)
# 💡 Memory Hook: Re-attaches your branch to tip of main branch
git rebase main

# 27. Cherry-pick specific commit hash into current branch
# 💡 Memory Hook: Plucks single specific commit from another branch
git cherry-pick a1b2c3d

# 28. Delete local branch forcefully (-D)
git branch -D feature/old-branch

# 29. Delete remote branch on GitHub
git push origin --delete feature/old-branch

# 30. GitHub Web Browser Shortcut: Press '.' on any GitHub repository page to open full VS Code Web!
```
