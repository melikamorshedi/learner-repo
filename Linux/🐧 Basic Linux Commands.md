# 🐧 Basic Linux Commands

These are the first commands every Linux user should know. They help you navigate the filesystem and manage files and directories.

---

# 📂 `pwd`

## ❓ What is it?

`pwd` stands for **Print Working Directory**.

## 🤔 Why use it?

- 📍 Shows your current location in the filesystem.
- 🧭 Helps you know where you are before running commands.

## 💻 Example

```bash
pwd
```

**Output**

```text
/home/sammy
```

---

# 📁 `cd`

## ❓ What is it?

`cd` stands for **Change Directory**.

## 🤔 Why use it?

- 📂 Move between directories.
- 🚀 Navigate the Linux filesystem.

## 💻 Examples

### Go to another directory

```bash
cd /usr/share
```

### Go back one directory

```bash
cd ..
```

### Go to your home directory

```bash
cd ~
```

or simply

```bash
cd
```

---

# 🗺️ Absolute Path

## ❓ What is it?

An **absolute path** is the complete path starting from the root directory (`/`).

## 🤔 Why use it?

- ✅ Always points to the same location.
- 🚫 Doesn't depend on your current directory.

## 💻 Example

```bash
cd /usr/bin
```

Even if you're somewhere else, you'll always end up in:

```text
/usr/bin
```

---

# 📋 `ls`

## ❓ What is it?

Lists files and directories.

## 🤔 Why use it?

- 👀 View directory contents.
- 📂 Check available files.

## 💻 Example

```bash
ls
```

---

# 📋 `ls -l`

## ❓ What is it?

Shows files in **long format**.

## 🤔 Why use it?

Displays:

- 📄 Permissions
- 👤 Owner
- 📦 File size
- 📅 Modification date

## 💻 Example

```bash
ls -l
```

---

# 👻 `ls -a`

## ❓ What is it?

Lists **all** files, including hidden ones.

## 🤔 Why use it?

- 👀 View hidden configuration files.
- ⚙️ Troubleshooting.

## 💻 Example

```bash
ls -a
```

---

# 📖 `less`

## ❓ What is it?

Views a text file one page at a time.

## 🤔 Why use it?

- 📜 Read large files.
- 🚀 Doesn't load the whole file into memory.

## 💻 Example

```bash
less /etc/services
```

### Useful Shortcuts

| Key     | Action                 |
| ------- | ---------------------- |
| `Space` | Next page              |
| `n`     | Next search result     |
| `N`     | Previous search result |
| `q`     | Quit                   |

---

# ✍️ `touch`

## ❓ What is it?

Creates an empty file or updates its timestamp.

## 🤔 Why use it?

- 📄 Create new files quickly.
- 🕒 Update modification time.

## 💻 Examples

```bash
touch file1
```

Create multiple files:

```bash
touch file2 file3
```

---

# 📁 `mkdir`

## ❓ What is it?

Creates directories.

## 🤔 Why use it?

- 📂 Organize your files.
- 🏗️ Build project structures.

## 💻 Examples

Create one directory

```bash
mkdir test
```

Create nested directories

```bash
mkdir -p some/other/directories
```

---

# 🚚 `mv`

## ❓ What is it?

Moves or renames files and directories.

## 🤔 Why use it?

- 📂 Move files.
- ✏️ Rename files or folders.

## 💻 Examples

Move a file

```bash
mv file1 test/
```

Rename a directory

```bash
mv test testing
```

---

# 📄 `cp`

## ❓ What is it?

Copies files and directories.

## 🤔 Why use it?

- 📑 Create backups.
- 📂 Duplicate files.

## 💻 Examples

Copy a file

```bash
cp file3 file4
```

Copy a directory

```bash
cp -r some again
```

---

# 🗑️ `rm`

## ❓ What is it?

Deletes files.

## 🤔 Why use it?

- 🧹 Remove unwanted files.

## 💻 Example

```bash
rm file4
```

Delete a directory recursively

```bash
rm -r again
```

> ⚠️ Be careful! Deleted files cannot usually be recovered.

---

# 📂 `rmdir`

## ❓ What is it?

Removes **empty** directories.

## 🤔 Why use it?

- 🧹 Delete folders that contain no files.

## 💻 Example

```bash
rmdir testing/example
```

---

# ✏️ `nano`

## ❓ What is it?

A simple terminal text editor.

## 🤔 Why use it?

- 📝 Edit configuration files.
- 📄 Create text files.

## 💻 Example

```bash
nano file1
```

Example content:

```text
Hello there.

Here is some text.

Another line.
```

Save:

- `Ctrl + O`

Exit:

- `Ctrl + X`

---

# 🧭 Navigation Example

```bash
pwd
cd /usr/share
cd locale
cd en/LC_MESSAGES
cd ..
cd ~
pwd
```











---

# 📚 Linux Navigation & File Management Cheat Sheet

| Command                 | 📝 Purpose                           | 💡 Example              |
| ----------------------- | ----------------------------------- | ---------------------- |
| `pwd`                   | Show current directory              | `pwd`                  |
| `cd directory`          | Change directory                    | `cd /usr/share`        |
| `cd ..`                 | Go to parent directory              | `cd ..`                |
| `cd ~`                  | Go to home directory                | `cd ~`                 |
| `cd`                    | Go to home directory                | `cd`                   |
| `ls`                    | List files and directories          | `ls`                   |
| `ls -l`                 | Long listing format                 | `ls -l`                |
| `ls -a`                 | Show hidden files                   | `ls -a`                |
| `touch file`            | Create an empty file                | `touch notes.txt`      |
| `mkdir dir`             | Create a directory                  | `mkdir projects`       |
| `mkdir -p dir/subdir`   | Create nested directories           | `mkdir -p app/src`     |
| `mv source destination` | Move or rename files/directories    | `mv file1 backup/`     |
| `cp file copy`          | Copy a file                         | `cp file1 file2`       |
| `cp -r dir copy`        | Copy a directory recursively        | `cp -r project backup` |
| `rm file`               | Delete a file                       | `rm notes.txt`         |
| `rm -r directory`       | Delete a directory and its contents | `rm -r project`        |
| `rmdir directory`       | Remove an empty directory           | `rmdir empty_folder`   |
| `nano file`             | Edit a text file                    | `nano config.txt`      |
| `less file`             | View a file page by page            | `less /etc/services`   |

---

# ⌨️ `less` Navigation Shortcuts

| Key       | Action                  |
| --------- | ----------------------- |
| `↑` / `↓` | Scroll one line         |
| `Space`   | Next page               |
| `b`       | Previous page           |
| `g`       | Go to beginning of file |
| `G`       | Go to end of file       |
| `/text`   | Search forward          |
| `n`       | Next search result      |
| `N`       | Previous search result  |
| `q`       | Quit `less`             |

---

# 📁 Path Quick Reference

| Path                   | Meaning                       |
| ---------------------- | ----------------------------- |
| `/`                    | Root directory                |
| `~`                    | Current user's home directory |
| `.`                    | Current directory             |
| `..`                   | Parent directory              |
| `/usr/bin`             | Absolute path                 |
| `Documents/report.txt` | Relative path                 |

---

# 🚀 Most Common Workflow

```bash
pwd                 # Where am I?
ls                  # What's here?
cd Documents        # Enter a directory
touch notes.txt     # Create a file
nano notes.txt      # Edit it
less notes.txt      # View it
cp notes.txt backup.txt
mv backup.txt Backup/
rm notes.txt
cd ~                # Return home
```

---

# 🧠 Memory Tips

| Remember | Meaning                             |
| -------- | ----------------------------------- |
| `pwd`    | **P**rint **W**orking **D**irectory |
| `cd`     | **C**hange **D**irectory            |
| `ls`     | **L**i**s**t files                  |
| `cp`     | **C**o**p**y                        |
| `mv`     | **M**o**v**e or rename              |
| `rm`     | **R**e**m**ove                      |
| `mkdir`  | **M**a**k**e **Dir**ectory          |
| `rmdir`  | Remove empty directory              |
| `touch`  | Create an empty file                |
| `nano`   | Terminal text editor                |
| `less`   | Read files page by page             |





