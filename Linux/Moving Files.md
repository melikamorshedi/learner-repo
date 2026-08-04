# Moving Files





# 🚚 `mv`

## ❓ What is it?

`mv` stands for **Move**.

It is used to **move** or **rename** files and directories.

---

## 🤔 Why use it?

- 📂 Move files to another directory.
- 📁 Move directories.
- ✏️ Rename files or folders.
- 🧹 Organize your filesystem.

---

## 💻 Basic Syntax

```bash
mv SOURCE DESTINATION
```

---

# 📂 Move a File

## ❓ What is it?

Moves a file to another directory.

## 🤔 Why use it?

Move files without creating a copy.

## 💻 Example

```bash
mv file.txt Documents/
```

---

# 📂 Move Multiple Files

## ❓ What is it?

Moves several files at the same time.

## 🤔 Why use it?

Save time when moving multiple files.

## 💻 Example

```bash
mv file1.txt file2.txt file3.txt Documents/
```

Move all text files:

```bash
mv *.txt Documents/
```

---

# ✏️ Rename a File

## ❓ What is it?

Changes a file's name.

## 🤔 Why use it?

Rename a file without changing its location.

## 💻 Example

```bash
mv old_name.txt new_name.txt
```

---

# 📁 Move a Directory

## ❓ What is it?

Moves an entire directory to another location.

## 🤔 Why use it?

Organize projects or folders.

## 💻 Example

```bash
mv project Documents/
```

---

# 📁 Rename a Directory

## ❓ What is it?

Changes the name of a directory.

## 🤔 Why use it?

Rename folders without moving them.

## 💻 Example

```bash
mv old_project new_project
```

---

# 🛡️ `-n`

## ❓ What is it?

Prevents overwriting existing files.

## 🤔 Why use it?

Protect important files from being replaced.

## 💻 Example

```bash
mv -n report.txt Documents/
```

---

# ❓ `-i`

## ❓ What is it?

Interactive mode.

## 🤔 Why use it?

Ask before replacing an existing file.

## 💻 Example

```bash
mv -i report.txt Documents/
```

Example prompt:

```text
mv: overwrite 'Documents/report.txt'?
```

---

# 💾 `-b`

## ❓ What is it?

Creates a backup before overwriting.

## 🤔 Why use it?

Keep a copy of the original file.

## 💻 Example

```bash
mv -b report.txt Documents/
```

Result:

```text
report.txt
report.txt~
```

---

# 🏷️ `-S`

## ❓ What is it?

Changes the backup file extension.

## 🤔 Why use it?

Use a custom backup suffix.

## 💻 Example

```bash
mv -S .bak -b report.txt Documents/
```

Result:

```text
report.txt
report.txt.bak
```

---

# 🔄 `-u`

## ❓ What is it?

Update mode.

## 🤔 Why use it?

Move a file **only if it is newer** than the destination or if the destination doesn't exist.

## 💻 Example

```bash
mv -u report.txt Documents/
```

---

# ⚡ `-f`

## ❓ What is it?

Force mode.

## 🤔 Why use it?

Overwrite existing files without asking.

## 💻 Example

```bash
mv -f report.txt Documents/
```

---

# 📢 `-v`

## ❓ What is it?

Verbose mode.

## 🤔 Why use it?

Show exactly what `mv` is doing.

## 💻 Example

```bash
mv -v report.txt Documents/
```

Output:

```text
renamed 'report.txt' -> 'Documents/report.txt'
```

---

# 📚 `mv` Cheat Sheet

| Command                   | 📝 Purpose               | 💡 Example                  |
| ------------------------- | ----------------------- | -------------------------- |
| `mv file dir/`            | Move a file             | `mv notes.txt Documents/`  |
| `mv file1 file2 dir/`     | Move multiple files     | `mv a.txt b.txt Docs/`     |
| `mv *.txt dir/`           | Move matching files     | `mv *.txt Docs/`           |
| `mv old new`              | Rename a file           | `mv old.txt new.txt`       |
| `mv dir destination/`     | Move a directory        | `mv project Backup/`       |
| `mv old_dir new_dir`      | Rename a directory      | `mv app app-old`           |
| `mv -i file dir/`         | Ask before overwrite    | `mv -i file Docs/`         |
| `mv -n file dir/`         | Never overwrite         | `mv -n file Docs/`         |
| `mv -f file dir/`         | Force overwrite         | `mv -f file Docs/`         |
| `mv -u file dir/`         | Move only if newer      | `mv -u file Docs/`         |
| `mv -b file dir/`         | Backup before overwrite | `mv -b file Docs/`         |
| `mv -S .bak -b file dir/` | Custom backup suffix    | `mv -S .bak -b file Docs/` |
| `mv -v file dir/`         | Show operation details  | `mv -v file Docs/`         |

---

# 🧠 Memory Tips

| Option | Meaning                   |
| ------ | ------------------------- |
| `-i`   | 🙋 Interactive (ask first) |
| `-n`   | 🚫 No overwrite            |
| `-f`   | ⚡ Force overwrite         |
| `-u`   | 🔄 Update only if newer    |
| `-b`   | 💾 Backup before overwrite |
| `-S`   | 🏷️ Backup suffix           |
| `-v`   | 📢 Verbose (show details)  |