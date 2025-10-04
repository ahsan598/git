# 📂 Repository Setup & Remote Handling


### 📂 Creating a New Git Repository (Local & Remote)

✅ **Option 1: Create Local → Link to Remote**

| Step | Command                                   | Description                                |
| ---- | ----------------------------------------- | ------------------------------------------ |
| 1️⃣  | `git init`                                | Initialize empty Git repo locally          |
| 2️⃣  | `git add .`                               | Stage all current files                    |
| 3️⃣  | `git commit -m "Initial commit"`          | Make first commit                          |
| 4️⃣  | Create repo on GitHub/GitLab (no README!) | Manually (via browser)                     |
| 5️⃣  | `git remote add origin <repo-url>`        | Link local repo to remote                  |
| 6️⃣  | `git branch -M main`                      | Rename default branch to `main` (optional) |
| 7️⃣  | `git push -u origin main`                 | Push local code to remote                  |


✅ **Option 2: Clone Remote Repo → Work Locally**

| Step | Command                        | Description                          |
| ---- | ------------------------------ | ------------------------------------ |
| 1️⃣  | `git clone <repo-url>`         | Clone the remote repo to your system  |
| 2️⃣  | `cd <repo-name>`               | Go into the cloned repo folder        |
| 3️⃣  | `git status` / `git add`, etc. | Make changes, commit, and push        |


### 📝 Pro Tip
- Use `git remote rename <old> <new>` if origin name needs to change (rare).
- Use `git remote remove origin` and `add` again if it gets corrupted.

---

### ✅ Fix: Local branch is behind remote — pull first, then push

| Step | Command                         | Description                                                                        |
| ---- | ------------------------------- | -----------------------------------------------------------------------------------|
| 1️⃣  | `git pull --rebase origin main`  | 🔄 **Pulls latest changes** from GitHub (remote `main`) and **applies your local commits on top** of it. This avoids a messy merge commit and keeps history clean.                                             |
| 2️⃣  | `git push origin main`           | 📤 **Pushes your updated local branch** (now in sync with remote) to GitHub. No rejection now, since your local branch is up to date.                                                                         |


###  What’s going on here?

- The error you saw (`non-fast-forward`) happens when:
  - Someone else (or you, from another machine) pushed commits to GitHub.
  - Your local repo doesn't have those commits.
  - Git refuses your push to prevent accidentally overwriting those changes.


### 💡 Why `--rebase`?

- `git pull --rebase` avoids an extra merge commit and keeps the commit history linear and clean.
- Without `--rebase`, `git pull` does a merge, which might clutter your history with unnecessary merge commits like:
> Merge branch 'main' of github.com:...


### 📌 Note:

- If there are **conflicts during rebase**, Git will ask you to:
  - Resolve the conflict manually.
  - Stage the resolved files using `git add`.
  - Continue the rebase using `git rebase --continue`.

### ✅ Final Tip:

Use this fix **whenever your push gets rejected** due to being "**behind**". It ensures you're not overwriting someone else's work and that your changes cleanly stack on top of the latest code.
