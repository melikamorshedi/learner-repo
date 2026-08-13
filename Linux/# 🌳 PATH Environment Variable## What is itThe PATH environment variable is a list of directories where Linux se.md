~~~bash
# 🌳 PATH Environment Variable

## What is it?

The **PATH** environment variable is a list of directories where Linux searches for executable programs (commands).

When you type a command like:

```bash
ls
```

Linux does **not** magically know where `ls` is located.

Instead, it checks each directory listed inside the **PATH** variable until it finds the executable.

---

## Why use it?

Without PATH, you would need to type the full path for every command.

Instead of:

```bash
ls
```

you would have to type:

```bash
/bin/ls
```

PATH makes commands shorter and easier to use.

---

## How PATH Works

Suppose your PATH contains:

```text
/usr/local/bin
/usr/bin
/bin
```

When you type:

```bash
date
```

Linux searches in this order:

```
1. /usr/local/bin/date
2. /usr/bin/date
3. /bin/date
```

The first matching executable is executed.

If Linux cannot find it anywhere:

```
bash: date: command not found
```

---

## View Your Current PATH

```bash
echo $PATH
```

Example output:

```text
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
```

Directories are separated by **colons (`:`)**.

---

## Display PATH More Readably

Instead of one long line:

```bash
echo $PATH
```

display each directory on its own line:

```bash
echo "${PATH//:/$'\n'}"
```

Output:

```text
/usr/local/sbin
/usr/local/bin
/usr/sbin
/usr/bin
/sbin
/bin
```

This is much easier to read.

---

# What Happens When You Run a Command?

Suppose you type:

```bash
ping google.com
```

Linux performs these steps:

1. Reads your command.
2. Looks through every directory in `$PATH`.
3. Finds the executable.
4. Executes the program.
5. Displays the output.
6. Waits for the next command.

---

## Find Where a Command Is Located

### Using `which`

```bash
which ls
```

Output:

```text
/bin/ls
```

Another example:

```bash
which nano
```

Output:

```text
/usr/bin/nano
```

---

### Using `command -v`

```bash
command -v python3
```

Output:

```text
/usr/bin/python3
```

This is more reliable than `which` because it's a Bash built-in.

---

### Using `type`

```bash
type ls
```

Output:

```text
ls is /usr/bin/ls
```

Unlike `which`, `type` also tells you if something is:

- an alias
- a shell builtin
- a function
- an executable file

Example:

```bash
type cd
```

Output:

```text
cd is a shell builtin
```

---

## Show Every Matching Command

Sometimes multiple versions of a command exist.

```bash
which -a python
```

or

```bash
type -a python
```

Example:

```text
/usr/bin/python
/usr/local/bin/python
```

---

# Add a Directory to PATH

Imagine you have your own scripts inside:

```text
~/scripts
```

Normally you'd have to run:

```bash
~/scripts/backup.sh
```

Instead, add the directory to PATH.

---

## Temporary PATH

Only lasts until the terminal closes.

```bash
export PATH="$HOME/scripts:$PATH"
```

Verify:

```bash
echo $PATH
```

Now you can simply run:

```bash
backup.sh
```

from anywhere.

---

## Permanent PATH

Open:

```bash
nano ~/.bashrc
```

Add:

```bash
export PATH="$HOME/scripts:$PATH"
```

Save the file.

Reload:

```bash
source ~/.bashrc
```

Now the change remains after reboot.

---

# Remove a Directory from PATH

PATH is usually configured in:

```text
~/.bashrc
```

or system-wide in:

```text
/etc/environment
```

Simply remove the unwanted directory and reload:

```bash
source ~/.bashrc
```

---

# PATH Priority

Linux searches directories **from left to right**.

Example:

```text
PATH=/home/meli/bin:/usr/local/bin:/usr/bin:/bin
```

If `python` exists in:

```
/home/meli/bin
/usr/bin
```

Linux executes:

```
/home/meli/bin/python
```

because it appears first.

This is called **PATH precedence**.

---

# Executing Programs Without PATH

Suppose you're inside a directory containing:

```text
hello.sh
```

Typing:

```bash
hello.sh
```

usually gives:

```text
command not found
```

because the current directory (`.`) is **not** in PATH.

Instead use:

```bash
./hello.sh
```

The `./` means:

> Execute the file from the current directory.

---

# Common PATH Directories

| Directory | Purpose |
|-----------|---------|
| `/bin` | Essential user commands |
| `/usr/bin` | Most user applications |
| `/usr/local/bin` | Locally installed programs |
| `/sbin` | System administration commands |
| `/usr/sbin` | Administrative utilities |
| `~/bin` | User's personal commands |

---

# Useful Commands

### Show PATH

```bash
echo $PATH
```

---

### Find command location

```bash
which docker
```

---

### Better command lookup

```bash
command -v docker
```

---

### Display command type

```bash
type docker
```

---

### Show all matches

```bash
type -a python
```

---

### Add directory temporarily

```bash
export PATH="$HOME/scripts:$PATH"
```

---

### Reload Bash configuration

```bash
source ~/.bashrc
```

---

# Common Problems

## command not found

Possible causes:

- Program isn't installed.
- Directory isn't in PATH.
- File isn't executable.

Check:

```bash
which command_name
```

or

```bash
command -v command_name
```

---

## Permission denied

The file exists but isn't executable.

Give execute permission:

```bash
chmod +x script.sh
```

Then run:

```bash
./script.sh
```

---

# PATH vs Current Directory

| Command | Meaning |
|----------|---------|
| `ls` | Search PATH for `ls` |
| `/bin/ls` | Execute using absolute path |
| `./script.sh` | Execute from current directory |

---

# Tips

💡 PATH only stores **directories**, not individual commands.

💡 Linux searches directories **from left to right**.

💡 Avoid adding duplicate directories to PATH.

💡 Use `$HOME` instead of hardcoding your username.

Example:

```bash
export PATH="$HOME/bin:$PATH"
```

instead of

```bash
export PATH="/home/meli/bin:$PATH"
```

---

# Best Use Cases

Use PATH when you want to:

- Run your own scripts from anywhere.
- Install custom software.
- Configure development tools.
- Set up programming environments.
- Customize your shell environment.

---

# Cheat Sheet

| Command | Description |
|----------|-------------|
| `echo $PATH` | Show PATH |
| `echo "${PATH//:/$'\n'}"` | Display PATH one directory per line |
| `which ls` | Find command location |
| `command -v ls` | Better way to find a command |
| `type ls` | Show command type |
| `type -a python` | Show all matching executables |
| `export PATH="$HOME/bin:$PATH"` | Temporarily add a directory |
| `nano ~/.bashrc` | Permanently modify PATH |
| `source ~/.bashrc` | Reload Bash configuration |
| `./script.sh` | Run a script from the current directory |

---

📌 **LPIC-1 / DevOps Tip**

Understanding the **PATH** variable is essential for Linux administration. You'll frequently modify it when installing tools like **Docker**, **kubectl**, **Terraform**, **AWS CLI**, **Go**, **Node.js**, or when creating your own Bash scripts. A solid understanding of PATH also helps you troubleshoot **"command not found"** errors and control which version of a program Linux executes.
~~~

