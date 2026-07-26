# EXERCISE 03: SSH Key

## Subject Requirements
* **Turn-in directory:** `ex03/`
* **Files to turn in:** `id_rsa_pub`
* **Allowed functions:** None
* **Objective:** Generate an SSH key pair, upload the public key to the intra/Git server, and submit a copy of the public key in your repository.

---

## Key Concepts & Core Ideas

### 1. Asymmetric Cryptography (Public vs. Private Keys)
SSH (Secure Shell) keys come in pairs:
* **The Private Key (`id_rsa`):** This is your secret password. It stays entirely on your local machine and **MUST NEVER** be shared, pushed to GitHub, or given to anyone else.
* **The Public Key (`id_rsa.pub`):** This is the lock you give to servers (like GitHub or the 1337 Intranet). It is safe to share with the world. When your private key interacts with this public lock, the server knows it is you.
---

## The Solution

Here are the standard steps to complete this exercise:

**Step 1: Generate the SSH Key Pair**
If you do not already have an SSH key, generate an RSA key:
```bash
ssh-keygen -t rsa -b 4096
# 42 school
