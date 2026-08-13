# 🔐 Linux Superuser & `sudo`

## What is the Root User?

`root` is the Linux user with the highest level of privileges.

The root user can:

- Modify system files
- Install or remove software
- Manage users
- Change system configuration
- Access almost everything on the system

---

# 👤 Regular User vs Root

| User         | Privileges         |
| ------------ | ------------------ |
| Regular user | Limited access     |
| `root`       | Full system access |

For everyday work, Linux recommends using a regular user and only using elevated privileges when necessary. 

---

# 👀 Check the Current User

### `whoami`

Shows the username of the current user.

```bash
whoami
```

### `id`

Shows information about the current user and their groups.

```bash
id
```

---

# ⚡ `sudo`

`sudo` allows a permitted regular user to run a command with elevated privileges.

Example:

```bash
sudo apt update
```

Instead of becoming root permanently, you normally use `sudo` only for the command that needs administrative privileges.

---

# 🔄 `su`

`su` allows you to switch to another user.

Switch to root:

```bash
su -
```

After switching, you can return to your previous user with:

```bash
exit
```

---

# 🔑 `sudo` vs `su`

| Command        | Purpose                                  |
| -------------- | ---------------------------------------- |
| `sudo command` | Run one command with elevated privileges |
| `su -`         | Switch to another user                   |
| `exit`         | Leave the current user session           |

---

# 🛡️ Why Use `sudo`?

Using `sudo` is generally safer than working as `root` all the time because administrative privileges are used only when needed.

This follows the **principle of least privilege**: give users only the permissions they need.

---

# 👥 Administrative Groups

Some Linux distributions use special groups to give users administrative privileges.

For example:

```bash
wheel
```

is commonly used on Red Hat-based systems, while Ubuntu commonly uses:

```bash
sudo
```

Users in these groups can be allowed to perform administrative tasks with `sudo`. 

---

# ⚙️ The `sudoers` File

The `sudoers` configuration controls which users can use `sudo` and which commands they can run.

The main configuration file is:

```bash
/etc/sudoers
```

Use `visudo` to safely edit it:

```bash
sudo visudo
```

> ⚠️ Do not casually edit `/etc/sudoers` with a normal text editor. `visudo` checks the configuration before saving.

---

# 🔒 Lock the Root Account

On systems where you need to lock the root account, one method is:

```bash
sudo passwd -l root
```

Unlock it:

```bash
sudo passwd -u root
```

The `-l` option locks the account and `-u` unlocks it. 

---

# 🧠 Simple Example

Imagine you want to install Nginx.

As a regular user:

```bash
apt install nginx
```

You may get a permission error.

Use:

```bash
sudo apt install nginx
```

Now the command runs with the required administrative privileges.

---

# 📝 Quick Reference

| Command               | Meaning                                |
| --------------------- | -------------------------------------- |
| `whoami`              | Show current username                  |
| `id`                  | Show user and group information        |
| `sudo command`        | Run a command with elevated privileges |
| `su -`                | Switch to another user/root            |
| `exit`                | Exit the current user session          |
| `sudo visudo`         | Safely edit sudo configuration         |
| `sudo passwd -l root` | Lock root                              |
| `sudo passwd -u root` | Unlock root                            |

---

# 💡 Remember

```text
Regular user
     ↓
   sudo
     ↓
Administrative command
```

You usually **do not need to work as root**. Use `sudo` when you need administrative privileges.