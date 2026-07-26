# EXERCISE 07: diff

## Subject Requirements
* **Turn-in directory:** `ex07/`
* **Files to turn in:** `b`
* **Allowed functions:** None
* **Objective:** Use a provided patch file (`sw.diff`) to transform file `a` into a new file `b`.

---

## Key Concepts: `diff` and `patch`

In software engineering, you often need to share code updates without sending the entire file again.
* **`diff`:** A command that analyzes two files and outputs only the exact differences (added, removed, or changed lines) between them.
* **`patch`:** The inverse command. It takes a file containing differences (like `sw.diff`) and applies those rules to an existing file to update it.

---

## ow to Solve This Problem

When you are given an original file (`a`) and a difference file (`sw.diff`), you must use `patch` to generate the target file (`b`).

**Step 1: Duplicate the original file**
Create `file b` as an exact copy of `file a` so you have a base to modify without destroying the original.
### Check the resources directory, then follow these commands:
1. Copy a into a new file b (so we have something to modify):

```bash
cp a b

```
2. Apply the patch to file b using the sw.diff rules:
``` bash
patch b < sw.diff

```
3. Verify the result!
``` bash
cat b

```
4. The Final Test
``` bash 
diff a b

```
If the output exactly matches the contents of the sw.diff file, your file b is perfectly correct.
