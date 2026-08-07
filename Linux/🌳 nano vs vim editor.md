

------

# 🌳 nano Command

## What is it?

`nano` is a simple, terminal-based text editor for Linux.

It allows you to create, edit, and save text files directly from the command line.

Unlike editors such as **vim** or **emacs**, Nano is beginner-friendly because it displays its keyboard shortcuts at the bottom of the screen.

------

## Why use it?

- Create new files
- Edit configuration files
- Write Bash scripts
- Modify source code
- Quick and easy to learn

------

## Install

Ubuntu/Debian:

```bash
sudo apt install nano
```

Fedora:

```bash
sudo dnf install nano
```

CentOS:

```bash
sudo yum install nano
```

------

## Basic Syntax

```bash
nano [options] filename
```

------

## Create a New File

```bash
nano notes.txt
```

If the file doesn't exist, Nano creates it automatically.

------

## Open an Existing File

```bash
nano notes.txt
```

------

## Edit the File

Simply start typing.

Nano immediately enters editing mode.

------

## Save a File

Press:

```text
Ctrl + O
```

Nano asks for the filename.

Press:

```text
Enter
```

to save.

------

## Exit Nano

Press:

```text
Ctrl + X
```

If you made changes, Nano asks:

```text
Save modified buffer?
```

Press:

```text
Y
```

to save

or

```text
N
```

to discard changes.

------

## Open a File as Root

Some system files require administrator privileges.

```bash
sudo nano /etc/hostname
```

------

## Useful Examples

### Edit the hosts file

```bash
sudo nano /etc/hosts
```

------

### Edit the hostname

```bash
sudo nano /etc/hostname
```

------

### Create a Bash script

```bash
nano hello.sh
```

Example:

```bash
#!/bin/bash

echo "Hello, World!"
```

------

## Common Nano Shortcuts

| Shortcut   | Action               |
| ---------- | -------------------- |
| `Ctrl + O` | Save file            |
| `Ctrl + X` | Exit Nano            |
| `Ctrl + K` | Cut current line     |
| `Ctrl + U` | Paste                |
| `Ctrl + W` | Search text          |
| `Ctrl + \` | Search and replace   |
| `Ctrl + G` | Help                 |
| `Ctrl + C` | Show cursor position |
| `Ctrl + _` | Go to line number    |
| `Alt + U`  | Undo                 |
| `Alt + E`  | Redo                 |

> **Note:** Undo/Redo is available in modern versions of Nano.

------

# Useful Options

### Create a backup before saving

```bash
nano -B file.txt
```

Creates:

```text
file.txt~
```

------

### Show cursor position

```bash
nano -c file.txt
```

Displays the current line and column.

------

### Enable automatic indentation

```bash
nano -i file.txt
```

Useful for programming.

------

### Enable syntax highlighting

```bash
nano -Y sh script.sh
```

Highlights Bash syntax.

------

## Common Problems

### nano: command not found

Nano is not installed.

Install it:

```bash
sudo apt install nano
```

------

### Permission denied

You don't have permission to edit the file.

Open it with:

```bash
sudo nano filename
```

or change the file permissions.

------

## Nano vs Vim

| Feature                       | Nano | Vim   |
| ----------------------------- | ---- | ----- |
| Easy to learn                 | ✅    | ❌     |
| Beginner friendly             | ✅    | ❌     |
| Built into most Linux systems | ✅    | ✅     |
| Powerful editing features     | ⭐⭐⭐  | ⭐⭐⭐⭐⭐ |
| Learning curve                | Low  | High  |

------

## Tips

💡 Nano displays its most important keyboard shortcuts at the bottom of the screen.

You don't need to memorize everything immediately.

------

## Best Use Cases

Use Nano when you need to:

- Edit Linux configuration files
- Write Bash scripts
- Quickly modify text files
- Make changes over SSH
- Learn Linux before moving to Vim

------

# Summary

| Command         | Description           |
| --------------- | --------------------- |
| `nano file.txt` | Open or create a file |
| `Ctrl + O`      | Save                  |
| `Enter`         | Confirm filename      |
| `Ctrl + X`      | Exit                  |
| `Ctrl + W`      | Search                |
| `Ctrl + K`      | Cut line              |
| `Ctrl + U`      | Paste                 |
| `Ctrl + \`      | Search and replace    |
| `Ctrl + G`      | Help                  |
| `Ctrl + C`      | Cursor position       |
| `Ctrl + _`      | Go to line            |
| `Alt + U`       | Undo                  |
| `Alt + E`       | Redo                  |

------

📌 **LPIC-1 / DevOps Tip**

Nano is the editor you'll most often use when working on remote Linux servers via SSH. You'll frequently use it to edit files such as:

- `/etc/hosts`
- `/etc/hostname`
- `/etc/fstab`
- `/etc/ssh/sshd_config`
- `/etc/nginx/nginx.conf`
- `/etc/docker/daemon.json`

Learning to navigate and edit these files efficiently with Nano is an essential Linux administration skill.

















---

# 🌳 vim Command

## What is it?

`vim` (**Vi IMproved**) is a powerful, terminal-based text editor for Linux and Unix systems.

Unlike Nano, Vim is **modal**, meaning it has different modes for editing, navigating, and executing commands.

Vim is one of the most popular editors among Linux administrators, programmers, and DevOps engineers because it is fast, lightweight, and available on almost every Linux system.

---

## Why use it?

- Edit configuration files
- Write Bash scripts
- Develop software
- Edit files on remote servers via SSH
- Navigate and edit text efficiently
- Available on almost every Linux distribution

---

## Install

Ubuntu/Debian:

```bash
sudo apt install vim
```

Fedora:

```bash
sudo dnf install vim
```

CentOS:

```bash
sudo yum install vim
```

---

## Basic Syntax

```bash
vim [options] filename
```

---

## Create a New File

```bash
vim notes.txt
```

If the file doesn't exist, Vim creates it when you save.

---

## Open an Existing File

```bash
vim notes.txt
```

---

## Vim Modes

Unlike Nano, Vim uses different modes.

| Mode        | Purpose                              |
| ----------- | ------------------------------------ |
| **Normal**  | Navigate and execute commands        |
| **Insert**  | Type and edit text                   |
| **Visual**  | Select text                          |
| **Command** | Save, quit, search, and run commands |

---

## Enter Insert Mode

Press:

```text
i
```

Now you can start typing.

---

## Return to Normal Mode

Press:

```text
Esc
```

---

## Save a File

Press:

```text
Esc
```

Then type:

```text
:w
```

Press:

```text
Enter
```

---

## Save and Exit

Press:

```text
Esc
```

Then type:

```text
:wq
```

or

```text
ZZ
```

---

## Exit Without Saving

Press:

```text
Esc
```

Then type:

```text
:q!
```

---

## Open a File as Root

Some system files require administrator privileges.

```bash
sudo vim /etc/hostname
```

---

## Useful Examples

### Edit the hosts file

```bash
sudo vim /etc/hosts
```

---

### Edit the hostname

```bash
sudo vim /etc/hostname
```

---

### Create a Bash script

```bash
vim hello.sh
```

Example:

```bash
#!/bin/bash

echo "Hello, World!"
```

---

## Basic Navigation

| Key  | Action            |
| ---- | ----------------- |
| `h`  | Move left         |
| `j`  | Move down         |
| `k`  | Move up           |
| `l`  | Move right        |
| `0`  | Beginning of line |
| `$`  | End of line       |
| `gg` | Beginning of file |
| `G`  | End of file       |

---

## Common Vim Shortcuts

| Shortcut   | Action                 |
| ---------- | ---------------------- |
| `i`        | Enter Insert Mode      |
| `Esc`      | Return to Normal Mode  |
| `:w`       | Save                   |
| `:q`       | Quit                   |
| `:wq`      | Save and Quit          |
| `:q!`      | Quit without saving    |
| `dd`       | Delete current line    |
| `yy`       | Copy current line      |
| `p`        | Paste                  |
| `u`        | Undo                   |
| `Ctrl + r` | Redo                   |
| `/text`    | Search                 |
| `n`        | Next search result     |
| `N`        | Previous search result |

---

# Useful Options

### Open in Read-only Mode

```bash
vim -R file.txt
```

---

### Open Multiple Files

```bash
vim file1.txt file2.txt
```

---

### Open at a Specific Line

```bash
vim +25 file.txt
```

Opens the file at line **25**.

---

### Enable Diff Mode

```bash
vim -d file1.txt file2.txt
```

Compare two files side by side.

---

## Common Problems

### vim: command not found

Vim isn't installed.

Install it:

```bash
sudo apt install vim
```

---

### Permission denied

You don't have permission to edit the file.

Open it with:

```bash
sudo vim filename
```

or change the file permissions.

---

## Nano vs Vim

| Feature                       | Nano |  Vim  |
| ----------------------------- | :--: | :---: |
| Easy to learn                 |  ✅   |   ❌   |
| Beginner friendly             |  ✅   |   ❌   |
| Built into most Linux systems |  ✅   |   ✅   |
| Powerful editing features     | ⭐⭐⭐  | ⭐⭐⭐⭐⭐ |
| Keyboard shortcuts shown      |  ✅   |   ❌   |
| Learning curve                | Low  | High  |

---

## Tips

💡 Always press **Esc** before entering a command like `:w` or `:q`.

💡 Press **i** to start typing.

💡 Press **Esc** when you're finished editing.

---

## Best Use Cases

Use Vim when you need to:

- Edit configuration files
- Program efficiently
- Work on remote Linux servers
- Perform advanced text editing
- Become a Linux administrator or DevOps engineer

---

# Summary

| Command        | Description           |
| -------------- | --------------------- |
| `vim file.txt` | Open or create a file |
| `i`            | Enter Insert Mode     |
| `Esc`          | Return to Normal Mode |
| `:w`           | Save                  |
| `:wq`          | Save and Exit         |
| `:q!`          | Quit without saving   |
| `dd`           | Delete line           |
| `yy`           | Copy line             |
| `p`            | Paste                 |
| `u`            | Undo                  |
| `Ctrl + r`     | Redo                  |
| `/text`        | Search                |
| `n`            | Next result           |
| `N`            | Previous result       |

---

📌 **LPIC-1 / DevOps Tip**

Vim is considered the standard text editor for Linux administrators.

You'll frequently use it to edit files such as:

- `/etc/hosts`
- `/etc/hostname`
- `/etc/fstab`
- `/etc/ssh/sshd_config`
- `/etc/nginx/nginx.conf`
- `/etc/docker/daemon.json`
- `/etc/systemd/system/*.service`

Learning Vim will greatly improve your productivity when working on Linux servers, especially over SSH, where it is often the only editor available.