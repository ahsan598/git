## 🚀 Repository Branch Reorganization: From Main to Feature and Master

### 🔧 1. Convert main → Feature branch

```sh
# Rename local branch from main to feature (new-branch)
git branch -m main new-branch

# Push 'new-branch' branch to remote
git push origin new-branch

# Set upstream
git push --set-upstream origin new-branch

# Delete 'main' branch from remote
git push origin --delete main
```


### ✳️ 2. Create a Clean master branch (as homepage)

```sh 
# Create a clean homepage branch (no history)
git checkout --orphan master

# Remove all files from index
git rm -rf .

# Add clean README.md
echo "# DevOps Cheatsheet" > README.md
echo "This repository contains cheatsheet for various DevOps tools." >> README.md
echo "## Branches" >> README.md

# Commit and push
git add README.md
git commit -m "Initial master branch with project overview"
git push origin master
```


### 🔁 3. Sync & Delete Branches

- Pull Latest Changes
```sh
git fetch
git pull

git pull origin branch-name
```

### 🧹 Delete Branch (Local & Remote)

- Delete local branch:
```sh
git branch -d branch-name     # If merged
git branch -D branch-name     # Force delete
```

- Delete remote branch:
```sh
git push origin --delete branch-name
```

> 🛑 Can't delete remote default branch (like main) until default branch is changed on GitHub UI.
> 
> **Fix:** Go to GitHub → Repo → Settings → Branches → Change default → Then delete


### ✅ 4. Final Verification

- List Remote Branches
```sh
git ls-remote --heads origin
```

- Remote-Tracking Branches
```sh
git branch -r
git branch -a           # Show all branches (local + remote)
```


### 🧹 5. Fix: Remove that stale origin/main reference locally
- Run this command to clean up your local remote-tracking branches:
```sh
git remote prune origin
```

- Now Verify:
```sh
git branch -r
```
