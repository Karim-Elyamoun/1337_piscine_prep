# EXERCISE 06: git_ignore.sh

## 📋 Subject Requirements
* **Turn-in directory:** `ex06/`
* **File to turn in:** `git_ignore.sh`
* **Allowed functions:** None
* **Objective:** Write a Shell script that lists all existing files currently ignored by your local Git repository.

---

## 💡 Key Concepts & Core Ideas

### 1. The Two Conditions of an Ignored File
For a file to be outputted by this script, two conditions must be true simultaneously:
1. **Rule exists:** A rule in `.gitignore` (or global ignore patterns) specifies that the file pattern should be ignored.
2. **File exists:** The physical file actually exists on the disk right now.

### 2. Why `git ls-files` instead of `git status`?
* `git status` prints human-readable headers, footers, and formatting.
* `git ls-files` is a plumbing command designed for scripts that outputs raw file paths (one per line).

### 3. Understanding the Flags
* `-o` / `--others`: Tells Git to inspect **untracked** files on disk.
* `-i` / `--ignored`: Filters the output to show **only** files matching ignore rules.
* `--exclude-standard`: Tells Git to respect standard ignore configurations (e.g., local `.gitignore`, `.git/info/exclude`, and global gitignores).

> **Note:** Without `--others` (`-o`), `--ignored` will fail to find ignored untracked files on disk!

---

## 🛠️ The Solution

Inside `git_ignore.sh`:

```bash
#!/bin/bash
git ls-files --others --ignored --exclude-standard
