
# 🔄 Renaming a GitHub Repository (Local & Remote) with Advanced Git Commands

This guide explains how to rename a GitHub repository **locally and remotely** using professional `.git` commands and good practices.

---

## 📚 Table of Contents

1. [Goal](#goal)
2. [1. Rename the Repository on GitHub (Remote)](#1-rename-the-repository-on-github-remote)
3. [2. Rename the Local Folder (Optional)](#2-rename-the-local-folder-optional)
4. [3. Update the Remote URL Locally](#3-update-the-remote-url-locally)
5. [4. Test the Setup](#4-test-the-setup)
6. [Bonus: Advanced Git Tips](#bonus-advanced-git-tips)

---

## Goal

Rename your GitHub repository from `repoNameOld` to `repoNameNew`, and reflect this change both locally and remotely, using best practices and advanced Git commands.

---

##  1. Rename the Repository on GitHub (Remote)

1. Go to your repository:
   ```
   https://github.com/your-username/repoNameOld
   ```
2. Navigate to **Settings** (⚙️).
3. Change the repository name to:
   ```
   repoNameNew
   ```
4. GitHub will automatically redirect the old repo name to the new one (temporary), so links won’t break immediately.

---

##  2. Rename the Local Folder (Optional)

If your local project folder is still named `repoNameOld`, rename it to match:

```bash
mv repoNameOld repoNameNew
cd repoNameNew
```

---

##  3. Update the Remote URL Locally

Check your current remote:

```bash
git remote -v
```

It should show:

```
origin  https://github.com/your-username/repoNameOld.git (fetch)
origin  https://github.com/your-username/repoNameOld.git (push)
```

Now, update it to the new remote URL:

```bash
git remote set-url origin https://github.com/your-username/repoNameNew.git
```

Verify:

```bash
git remote -v
```

---

##  4. Test the Setup

Make sure everything is working:

```bash
git fetch origin
git push origin main
```

> Replace `main` with the appropriate branch name (e.g., `master` or your default).

---

##  Bonus: Advanced Git Tips

- For teams: teammates must also update their remotes:
  ```bash
  git remote set-url origin https://github.com/your-username/repoNameNew.git
  ```

- Working with forks? Add an upstream:
  ```bash
  git remote add upstream https://github.com/original-owner/repoNameNew.git
  ```

- Rename the `origin` remote if needed:
  ```bash
  git remote rename origin repoNameNewRemote
  ```

---

> This guide ensures a clean, professional renaming process that avoids broken remotes or disconnected branches.
