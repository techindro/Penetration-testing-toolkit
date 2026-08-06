# 🐙 Module 03: Git & GitHub Comprehensive One-Liners & Examples

Essential Git one-liners and GitHub workflow tricks with clear practical examples.

---

## ⚡ 1. Git Daily One-Liners with Examples

```bash
# Example 1: Display clean single-line git history with branch graph
git log --oneline --graph --all
# Output:
# * a1b2c3d (HEAD -> main, origin/main) feat: add authentication API
# * e5f6g7h fix: resolve CORS policy error

# Example 2: Save uncommitted changes temporarily without committing
git stash
# Make urgent fix on another branch, then restore:
git stash pop

# Example 3: Undo the most recent commit while keeping all code changes in workspace
git reset --soft HEAD~1
# Usage: Use when you committed too early or forgot to add a file.

# Example 4: Discard all local uncommitted changes instantly (Fresh start)
git checkout .
# or
git restore .
# Usage: Reverts all files back to the last clean committed state.

# Example 5: Update the message of the last commit
git commit --amend -m "feat: complete login endpoint integration"
# Usage: Fixes typos in your most recent git commit message.

# Example 6: Rename local branch
git branch -m main master

# Example 7: Delete local and remote branch
git branch -d feature-login
git push origin --delete feature-login
```

---

## 🚀 2. GitHub Web & CLI Examples

```bash
# Example 1: Clone repository using SSH key
git clone git@github.com:techindro/Penetration-testing-toolkit.git

# Example 2: Test GitHub SSH connection
ssh -T git@github.com
# Output: Hi techindro! You've successfully authenticated, but GitHub does not provide shell access.

# Example 3: GitHub Web Browser Shortcut
# Open any GitHub repo (e.g. github.com/facebook/react), press '.' (Period key).
# Result: Launches full VS Code editor directly in your web browser!
```
