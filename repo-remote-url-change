
### 📂 Repository Remote URL Changes

| 🔧 Command                            | 💬 What It Does                                              |
| --------------------------------------| ------------------------------------------------------------- |
| `git remote -v`                       | Check current remote URL (origin)                             |
| `git remote set-url origin <new-url>` | Update the remote URL after repo name or host changes         |
| `git remote get-url origin`           | Verify that the remote URL was updated correctly              |
| `git push -u origin <branch>`         | Set upstream again (optional if push fails due to URL change) |
| `git remote rename origin upstream`   | Rename existing remote (e.g., origin → upstream) |


### Examples:

- Renaming repo on GitHub:
```sh
git remote set-url origin https://github.com/username/new-repo-name.git
```
- Verifying the remote repo after rename:

```sh
git remote show origin
```

---

### 🗑️ How to Delete the Repo

| Action                    | Command / Steps                           |
| ------------------------- | ----------------------------------------- |
| Delete repo on GitHub     | Go to repo → Settings → Delete repository |
| Delete repo locally       | `rm -rf <repo-folder>`                    |
| Remove Git tracking       | `rm -rf .git`                             |
| Remove remote from local  | `git remote remove origin`                |
| Reconnect to new repo URL | `git remote add origin <new-url>`         |


> ⚠️ **Warning:** Use carefully — especially `rm -rf` as it cannot be undone. Double-check folder names and URLs before running commands.
> 
> Deleting the `.git` folder will permanently remove all Git history. It cannot be recovered without a backup.
