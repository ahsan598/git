# `.gitkeep` Guide

This document explains the purpose of the `.gitkeep` file and when to use it alongside `.gitignore`.


### ❓ What is `.gitkeep`?

Git does not track empty folders. So, if you want to preserve an empty folder in your Git repo, you can create a placeholder file named `.gitkeep`.

- `.gitkeep` is not a Git feature—it's a naming convention.
- It allows you to track an otherwise empty directory.


### 🧠 When Should You Use `.gitkeep`?

| Use Case                               | Description                                       |
| -------------------------------------- | ------------------------------------------------- |
| Preserving empty folders               | To keep folders like `logs/`, `uploads/`, `temp/` |
| Pre-creating required directories      | Useful in CI/CD pipelines or project scaffolds    |
| Shared folders that will receive files | Ensures folder exists for runtime-generated files |


### 🧾 Example `.gitkeep` File

```sh
mkdir logs
touch logs/.gitkeep
git add logs/.gitkeep
```

> Now `logs/` folder will be tracked in the repository.



### ❗ `.gitkeep` vs `.gitignore`

| Concept      | Purpose                                        |
| ------------ | ---------------------------------------------- |
| `.gitignore` | Ignore files or folders from Git tracking      |
| `.gitkeep`   | Include empty folders by tracking a dummy file |

You can use both together. For example:
```sh
logs/
!logs/.gitkeep
```

> This will ignore everything inside `logs/`, but still keep the `.gitkeep` file.


### ✅ Best Practices for `.gitkeep`
- Use only in empty folders you want to keep.
- Don’t use for real content — it's a placeholder only.
- Document its use so your team understands why it exists.
