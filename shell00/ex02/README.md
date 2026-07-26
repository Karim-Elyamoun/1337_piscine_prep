# EXERCISE 02: Oh yeah, mooore...

## 📋 Subject Requirements
* **Turn-in directory:** `ex02/`
* **Files to turn in:** `exo2.tar`
* **Allowed functions:** None
* **Objective:** Create specific files and directories with exact permissions, sizes, modification dates, and link structures so that running `ls -l` perfectly matches the expected output. Finally, compress them into a `.tar` archive.

---

## 💡 Key Concepts & Core Ideas

This exercise tests your mastery of the Linux filesystem. To achieve the exact `ls -l` output, you must manipulate several file attributes:

### 1. File Types
The first character of the `ls -l` output indicates the file type:
* `-` : Regular file (created with `touch`).
* `d` : Directory (created with `mkdir`).
* `l` : Symbolic link (created with `ln -s`).

### 2. Permissions (`chmod`)
You must translate the `rwx` (read, write, execute) strings into absolute octal numbers or symbolic modes to set the correct permissions.
* Example: `drwx--xr-x` = Directory with `715` permissions.
* Example: `-rwx--xr--` = File with `714` permissions.

### 3. Links (`ln`)
The number right after the permissions block represents the hard link count.
* **test3 & test5:** Share a link count of `2`, have the exact same size (`1` byte), and identical timestamps. This means they are **hard links** of each other (`ln test3 test5`).
* **test6:** Is a **symbolic link** pointing to the `test0` directory (`ln -s test0 test6`).

### 4. File Sizes
You must add exact byte counts to specific files using commands like `echo -n` to ensure they match the requirements (e.g., `4` bytes for `test1`, `2` bytes for `test4`).

### 5. Timestamps (`touch`)
The output requires specific modification dates (e.g., `Jun 1 20:47`). You must use the `touch -t` or `touch -m -d` command to artificially alter the timestamps of the files and directories.

---

## 🛠️ The Final Submission Command

Once all files and directories are perfectly configured, you must package them into a tape archive (`.tar` file) exactly as requested by the subject:

```bash
tar -cf exo2.tar *
