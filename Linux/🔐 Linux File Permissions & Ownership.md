# 🔐 Linux File Permissions & Ownership

Linux uses **ownership and permissions** to control who can access, modify, or execute files and directories.

---

# 👤 File Ownership

Every file has three ownership categories:

| Category    | Meaning                             |
| ----------- | ----------------------------------- |
| `u` / User  | The owner of the file               |
| `g` / Group | Users belonging to the file's group |
| `o` / Other | Everyone else                       |

You can see your groups with:

```bash
groups
```

---

# 🔑 File Permissions

Linux has three basic permissions:

| Permission | Symbol | Meaning         |
| ---------- | ------ | --------------- |
| Read       | `r`    | Read the file   |
| Write      | `w`    | Modify the file |
| Execute    | `x`    | Run the file    |

No permission is represented by:

```text
-
```

---

# 📄 Understanding `ls -l`

Use:

```bash
ls -l
```

Example:

```text
-rwxrw-r-- 1 user group 457 file.txt
```

The permission part is:

```text
-rwxrw-r--
```

Break it down:

```text
-   rwx   rw-   r--
│    │     │     │
│    │     │     └── Other
│    │     └──────── Group
│    └────────────── User
└─────────────────── File type
```

So:

```text
User  → rwx
Group → rw-
Other → r--
```

---

# 📁 Permissions on Directories

Permissions behave slightly differently for directories:

| Permission | Directory                  |
| ---------- | -------------------------- |
| `r`        | List contents              |
| `w`        | Create/delete files        |
| `x`        | Enter/access the directory |

---

# 🔢 Numeric Permissions

Linux represents permissions with numbers:

| Permission | Value |
| ---------- | ----- |
| `r`        | `4`   |
| `w`        | `2`   |
| `x`        | `1`   |
| `-`        | `0`   |

Add the values together:

```text
rwx = 4 + 2 + 1 = 7
rw- = 4 + 2 = 6
r-x = 4 + 1 = 5
r-- = 4
```

Example:

```text
755
```

means:

```text
User  → 7 → rwx
Group → 5 → r-x
Other → 5 → r-x
```

---

# 🛠️ `chmod`

`chmod` changes file permissions.

## Numeric Mode

```bash
chmod 755 script.sh
```

This gives:

```text
User  → rwx
Group → r-x
Other → r-x
```

---

## Symbolic Mode

You can change specific permissions using:

```text
u = user
g = group
o = other
a = all
```

Add permission:

```bash
chmod g+x file.txt
```

Remove permission:

```bash
chmod o-r file.txt
```

Give permission to everyone:

```bash
chmod a+x script.sh
```

---

# 👑 `chown`

`chown` changes the **owner** of a file.

```bash
sudo chown username file.txt
```

Change both user and group:

```bash
sudo chown username:groupname file.txt
```

Example:

```bash
sudo chown root:root file.txt
```

---

# 👥 `chgrp`

`chgrp` changes only the **group owner**.

```bash
sudo chgrp developers file.txt
```

---

# 🔍 Check Ownership and Permissions

Use:

```bash
ls -l file.txt
```

Example:

```text
-rwxr-xr-- 1 alice developers 120 file.txt
```

Here:

```text
Owner → alice
Group → developers
Permissions → rwxr-xr--
```

---

# ⚠️ Permission Precedence

Linux checks permissions in this order:

```text
User → Group → Other
```

If you are the **owner**, Linux uses the owner's permissions.

It does not give you additional permissions from the `group` or `other` sections just because you also belong to that group. :contentReference[oaicite:1]{index=1}

---

# 🧪 Simple Practice

Create a script:

```bash
touch script.sh
```

Check its permissions:

```bash
ls -l script.sh
```

Give yourself execute permission:

```bash
chmod u+x script.sh
```

Check again:

```bash
ls -l script.sh
```

Give everyone read and execute permission:

```bash
chmod 755 script.sh
```

Check:

```bash
ls -l script.sh
```

---

# 📝 Quick Reference

| Command  | Purpose                        |
| -------- | ------------------------------ |
| `ls -l`  | View permissions and ownership |
| `groups` | Show your groups               |
| `chmod`  | Change permissions             |
| `chown`  | Change owner                   |
| `chgrp`  | Change group                   |

---

# 💡 Remember

```text
              FILE
                │
       ┌────────┼────────┐
       ↓        ↓        ↓
     USER     GROUP    OTHER
       │        │        │
      rwx      rwx      rwx
```

And remember:

```text
r = 4
w = 2
x = 1
```

So:

```bash
755 = rwxr-xr-x
644 = rw-r--r--
```