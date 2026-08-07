# 📄 Creating, Copying, Moving, and Deleting Files in Linux





## 📁 Creating Files

### 🌳 `touch`

#### What is it?

Creates an empty file or updates the timestamp of an existing file.

#### Usage

```bash
touch file.txt
```

Create multiple files:

```bash
touch file1.txt file2.txt file3.txt
```

---

### 🌳 `echo`

#### What is it?

Creates a file and writes text into it.

#### Usage

```bash
echo "Hello Linux" > hello.txt
```

Append text instead of overwriting:

```bash
echo "Another line" >> hello.txt
```

---

### 🌳 `cat`

#### What is it?

Displays, creates, or combines files.

#### View a file

```bash
cat file.txt
```

#### Create a file with content

```bash
cat > notes.txt
```

Type your text:

```
Linux is awesome.
Docker is fun.
```

Save with:

```
Ctrl + D
```

---

# 📁 Creating Directories

### 🌳 `mkdir`

Create a directory:

```bash
mkdir myfolder
```

Create nested directories:

```bash
mkdir -p projects/python
```

---

# 📄 Copying Files

### 🌳 `cp`

Copy a file:

```bash
cp file.txt backup.txt
```

Copy a file into another directory:

```bash
cp file.txt backup/
```

Copy an entire directory:

```bash
cp -r myfolder backupfolder
```

---

# 🚚 Moving and Renaming

### 🌳 `mv`

Rename a file:

```bash
mv old.txt new.txt
```

Move a file:

```bash
mv new.txt Documents/
```

Move multiple files:

```bash
mv file1.txt file2.txt Documents/
```

---

# 🗑️ Deleting Files

### 🌳 `rm`

Delete a file:

```bash
rm file.txt
```

Delete with confirmation:

```bash
rm -i file.txt
```

Delete and show what was removed:

```bash
rm -v file.txt
```

Delete all `.txt` files:

```bash
rm *.txt
```

---

# 🗑️ Deleting Directories

### 🌳 `rmdir`

Delete an **empty** directory:

```bash
rmdir emptyfolder
```

---

### 🌳 `rm -r`

Delete a directory and everything inside it:

```bash
rm -r myfolder
```

Ask for confirmation:

```bash
rm -ri myfolder
```

Force deletion (Use with caution):

```bash
rm -rf myfolder
```

> ⚠️ `rm -rf` permanently deletes files. There is no Recycle Bin.

---

# 🔍 `touch` vs `echo` vs `cat`

| Command        | Best Used For                                  |
| -------------- | ---------------------------------------------- |
| `touch`        | Create an empty file                           |
| `echo`         | Create a file with one or two lines of text    |
| `cat >`        | Create a file and type multiple lines manually |
| `cat file.txt` | Display a file's contents                      |

---

# 🧪 Practice

Create a small project.

```bash
mkdir testlab
cd testlab
```

Create two files.

```bash
touch one.txt two.txt
```

Write some text.

```bash
echo "Hello Linux" > one.txt
```

Rename a file.

```bash
mv one.txt first.txt
```

Create a backup folder.

```bash
mkdir backup
```

Copy the file.

```bash
cp first.txt backup/
```

View the file.

```bash
cat backup/first.txt
```

Delete the second file.

```bash
rm two.txt
```

Go back one directory.

```bash
cd ..
```

Delete the entire project.

```bash
rm -r testlab
```

---

# 📝 Summary

| Task                    | Command                  |
| ----------------------- | ------------------------ |
| Create empty file       | `touch file.txt`         |
| Create file with text   | `echo "text" > file.txt` |
| Create file manually    | `cat > file.txt`         |
| View file               | `cat file.txt`           |
| Create folder           | `mkdir folder`           |
| Create nested folders   | `mkdir -p parent/child`  |
| Copy file               | `cp source destination`  |
| Copy folder             | `cp -r folder backup`    |
| Move file               | `mv file folder/`        |
| Rename file             | `mv old new`             |
| Delete file             | `rm file`                |
| Delete empty folder     | `rmdir folder`           |
| Delete non-empty folder | `rm -r folder`           |
