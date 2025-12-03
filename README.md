





## Creating ssh keys and connecting to GitHub/GitLab

### ✅ 1. Generate SSH key (Git key)

Use this when working with GitHub (pull/push via SSH).

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"   # Generate a new SSH key for GitHub
```

**Explanation:**
- `-t ed25519` → modern secure algorithm
- `-C` → comment (your email)

**When prompted:**
- File name: /home/youruser/.ssh/id_ed25519_github (better to name by purpose)
- Passphrase: optional but recommended.

**Example:**
Enter file in which to save the key (/home/user/.ssh/id_ed25519): id_ed25519_github

This creates two files:
```bash
~/.ssh/id_ed25519_github        # private key
~/.ssh/id_ed25519_github.pub    # public key
```

### ✅ 2. Add the key to the SSH agent
```bash
eval "$(ssh-agent -s)"  # Start ssh-agent
ssh-add ~/.ssh/id_ed25519_github    # Add your GitHub key
```

**Explanation:**
Allows the system to use the key automatically without typing the passphrase every time.

### ✅ 3. Copy public key to clipboard

Linux (common):
```bash
cat ~/.ssh/id_ed25519_github.pub
```
Copy the output manually.





Checking the existence of keys in the home directory
```bash
ls -al ~/.ssh
```