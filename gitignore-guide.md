# `.gitignore` Guide

This document explains the purpose of the `.gitignore` file and what **files/folders** are ignored in this project.


### 🔍 What is `.gitignore`?
The `.gitignore` file tells Git which files or folders not to track or commit to the repository.

**This is useful for:**
- Keeping sensitive or unnecessary files out of version control.
- Reducing clutter in your repository.
- Preventing large or automatically generated files from being committed.


### 🗃️ Common Files/Folders to Ignore
Here are some examples of what we typically ignore:
| Pattern             | Description                           |
| ------------------- | ------------------------------------- |
| `node_modules/`     | Node.js dependencies (auto-installed) |
| `*.log`             | Log files                             |
| `dist/` or `build/` | Build output folders                  |
| `.env`              | Environment variables (secrets)       |
| `*.tmp` or `*.swp`  | Temporary or swap files               |
| `.DS_Store`         | macOS file system metadata            |



### 🧾 Example `.gitignore` File

```sh
# Dependency directories
node_modules/
vendor/

# Build output
dist/
build/

# Logs
*.log

# Environment variables
.env

# Temporary files
*.tmp
*.swp

# OS metadata files
.DS_Store
Thumbs.db
```


### ✅ Best Practices
- Never commit **passwords, secrets, or API** keys—use `.gitignore` to exclude them.
- Customize your `.gitignore` depending on your project's language or tools.
- Use [gitignore.io](https://www.toptal.com/developers/gitignore) to generate a custom `.gitignore` template.


---

## 📄 .gitignore Cleanup & Verification Commands

| Command                            | Purpose                                                                          |
| ---------------------------------- | -----------------------------------------------------------------------------    |
| `git rm --cached <file>`           | Untrack any specific file                                                        |
| `git rm -r --cached .`             | Unstages all previously tracked files (resets Git index) without deleting them locally |
| `git add .`                        | Re-adds files and folders, this time following `.gitignore` rules                |
| `git commit -m "Apply .gitignore rules"` | Commits the updated file tracking state                                    |
| `git push`                         | Pushes changes to the remote repository                                          |
| `git check-ignore <file>`          | Checks if a file or folder is being ignored by `.gitignore` and shows matching rule    |


Example:

```sh
git rm -r --cached .

git add .

git commit -m "Remove tracked files to apply updated .gitignore"

git push origin <your-branch-name>

git check-ignore <file>

> If it shows nothing, that means: 🚫 The file is not being ignored.
```
