# Shell Basics



# 🐚 What is the Shell?

## What is it?

The **shell** is a command interpreter that acts as a bridge between **you** and the **Linux operating system**.

It reads the commands you type, interprets them, and asks the operating system (through the kernel) to execute them.

Simply put:

> **You → Shell → Kernel → Hardware**

---

## Why use it?

The shell allows you to:

- 💻 Run Linux commands
- 📂 Manage files and directories
- ⚙️ Configure the operating system
- 🐚 Write shell scripts
- 🤖 Automate repetitive tasks
- 🌐 Manage remote Linux servers via SSH

---

## How Does the Shell Work?

When you type a command, the shell follows these steps:

1. ⌨️ Reads your command.
2. 🔍 Searches for the program in the system's **PATH**.
3. 🚀 Executes the program.
4. 📤 Displays the output.
5. ⏳ Waits for the next command.

Example:

```bash
date
```

Output:

```text
Fri Aug 7 20:15:32 UTC 2026
```

---

# 🖥️ What is a Terminal?

## What is it?

A **terminal** (or **terminal emulator**) is the application where you interact with the shell.

Examples include:

- GNOME Terminal
- Konsole
- Xterm
- Kitty
- Alacritty
- Windows Terminal (with WSL)

The terminal **does not execute commands itself**.

It simply provides a window where the shell runs.

---

# 🔄 Terminal vs Shell

Many beginners confuse these two.

| Terminal                                      | Shell                              |
| --------------------------------------------- | ---------------------------------- |
| A program that displays a command-line window | A program that interprets commands |
| Provides the interface                        | Executes commands                  |
| Examples: GNOME Terminal, Konsole             | Examples: Bash, Zsh, Fish          |

Think of it like this:

```
Keyboard
    │
    ▼
Terminal
    │
    ▼
Shell
    │
    ▼
Kernel
    │
    ▼
Hardware
```

---

# 🧠 What is Bash?

## What is it?

**Bash** stands for:

> **Bourne Again SHell**

It is the default shell on most Linux distributions.

Bash is compatible with the original Unix **sh** shell while adding many new features.

---

## Why use Bash?

- Beginner friendly
- Powerful scripting language
- Command history
- Auto-completion
- Variables and loops
- Job control
- Available on almost every Linux system

---

# 🌟 Popular Linux Shells

| Shell  | Description                         |
| ------ | ----------------------------------- |
| `sh`   | Original Bourne Shell               |
| `bash` | Most common Linux shell             |
| `zsh`  | Bash with many extra features       |
| `fish` | Beginner-friendly interactive shell |
| `ksh`  | Korn Shell                          |
| `tcsh` | Enhanced C Shell                    |

---

# 📍 How to Check Your Current Shell

```bash
echo $SHELL
```

Example output:

```text
/bin/bash
```

---

# 📋 Show Installed Shells

```bash
cat /etc/shells
```

Example output:

```text
/bin/sh
/bin/bash
/bin/zsh
/usr/bin/fish
```

---

# 🔄 Change Your Default Shell

```bash
chsh -s /bin/zsh
```

> Log out and log back in for the change to take effect.

---

# 💬 What is a Shell Prompt?

The **shell prompt** is the text displayed before you type a command.

Example:

```bash
melika@ubuntu:~$
```

It usually contains:

- 👤 Username
- 💻 Computer name
- 📁 Current directory

The last character tells you your privilege level:

| Prompt | Meaning              |
| ------ | -------------------- |
| `$`    | Normal user          |
| `#`    | Root (administrator) |

---

# 📜 Command History

The shell remembers previously executed commands.

Use:

| Key  | Action           |
| ---- | ---------------- |
| ↑    | Previous command |
| ↓    | Next command     |

Example:

```bash
ls
pwd
cd Documents
```

Press **↑** to recall the previous command.

---

# ⚠️ Root User

The **root** user has full administrative privileges.

A root prompt looks like this:

```bash
root@server:~#
```

Be careful when working as root because commands can modify or delete any file on the system.

---

# 🎯 CLI vs GUI

| CLI                         | GUI                                  |
| --------------------------- | ------------------------------------ |
| Command Line Interface      | Graphical User Interface             |
| Uses text commands          | Uses windows, icons, and menus       |
| Faster for automation       | Easier for beginners                 |
| Preferred by administrators | Preferred for everyday desktop tasks |

---

# 💡 Tips

- The **terminal** is the application.
- The **shell** is the command interpreter.
- **Bash** is the most common Linux shell.
- Learn the shell—it is one of the most important Linux skills.

---

# 📚 Cheat Sheet

| Command            | Description               |
| ------------------ | ------------------------- |
| `echo $SHELL`      | Show current shell        |
| `cat /etc/shells`  | List installed shells     |
| `chsh -s /bin/zsh` | Change default shell      |
| `history`          | Show command history      |
| `clear`            | Clear the terminal screen |

---



```bash
       You
        │
        ▼
 Terminal Emulator
        │
        ▼
      Shell
  (Bash, Zsh...)
        │
        ▼
      Kernel
        │
        ▼
    Hardware
```