# Working with Files



# 📁 Files in Linux Command Line

Linux provides commands to create, view, edit, copy, move, rename, and delete files and directories.

------

# 📂 Navigating Files and Directories

Use these commands to move around the Linux filesystem.

| **Command** | **Purpose**                |
| ----------- | -------------------------- |
| `pwd`       | Show current directory     |
| `ls`        | List files and directories |
| `cd`        | Change directory           |
| `mkdir`     | Create a directory         |

Examples:

```bash
pwd
```

Show your current location.

```bash
ls
```

List the contents of the current directory.

```bash
cd Documents
```

Move into the `Documents` directory.

```bash
mkdir projects
```

Create a new directory.

------

# 📄 Creating and Viewing Files

Create an empty file:

```bash
touch notes.txt
```

Display file contents:

```bash
cat notes.txt
```

View a large file page by page:

```bash
less notes.txt
```

------

# 👀 Listing Files

Basic listing:

```bash
ls
```

Detailed information:

```bash
ls -l
```

Include hidden files:

```bash
ls -a
```

Combine both:

```bash
ls -la
```

------

# 📋 Copying Files — `cp`

Copy a file:

```bash
cp file.txt backup.txt
```

Copy a file to another directory:

```bash
cp file.txt Documents/
```

Copy multiple files:

```bash
cp file1.txt file2.txt Documents/
```

Copy a directory and its contents:

```bash
cp -r project/ backup/
```

------

# 🔀 Moving and Renaming — `mv`

Rename a file:

```bash
mv old.txt new.txt
```

Move a file:

```bash
mv file.txt Documents/
```

Move and rename at the same time:

```bash
mv file.txt Documents/report.txt
```

💡 Linux uses `mv` for both **moving** and **renaming**.

------

# 🗑️ Removing Files and Directories

Remove a file:

```bash
rm file.txt
```

Remove an empty directory:

```bash
rmdir empty-directory/
```

Remove a directory and its contents:

```bash
rm -r project/
```

⚠️ `rm` normally does not move files to a recycle bin. Deleted files may not be easily recoverable.

------

# 🔗 Hard and Soft Links

Create a hard link:

```bash
ln file.txt hard-link.txt
```

Create a symbolic (soft) link:

```bash
ln -s file.txt soft-link.txt
```

Check inode numbers:

```bash
ls -li
```

A hard link shares the same inode as the original file.

A symbolic link points to the original file's **path**.

------

# 📝 Editing Files with Vim

Open or create a file:

```bash
vim file.txt
```

Enter Insert Mode:

```text
i
```

Return to Normal Mode:

```text
Esc
```

Save:

```text
:w
```

Save and exit:

```text
:wq
```

Exit without saving:

```text
:q!
```

Some useful Normal Mode commands:

| **Command** | **Purpose**       |
| ----------- | ----------------- |
| `dd`        | Delete a line     |
| `yy`        | Copy a line       |
| `p`         | Paste             |
| `u`         | Undo              |
| `Ctrl+r`    | Redo              |
| `/word`     | Search for `word` |

------

# 🧪 Simple Practice

Create a directory:

```bash
mkdir linux-practice
```

Enter it:

```bash
cd linux-practice
```

Create a file:

```bash
touch notes.txt
```

Add some content:

```bash
echo "Linux is powerful" > notes.txt
```

Read the file:

```bash
cat notes.txt
```

Create a copy:

```bash
cp notes.txt backup.txt
```

Rename the copy:

```bash
mv backup.txt old-notes.txt
```

Create a symbolic link:

```bash
ln -s notes.txt notes-link.txt
```

Check everything:

```bash
ls -li
```

------

# 📝 Quick Reference

| **Command** | **Purpose**              |
| ----------- | ------------------------ |
| `pwd`       | Show current directory   |
| `ls`        | List files               |
| `cd`        | Change directory         |
| `touch`     | Create an empty file     |
| `mkdir`     | Create a directory       |
| `cat`       | Display file contents    |
| `less`      | View files page by page  |
| `cp`        | Copy files/directories   |
| `mv`        | Move or rename           |
| `rm`        | Remove files             |
| `rmdir`     | Remove empty directories |
| `ln`        | Create a hard link       |
| `ln -s`     | Create a symbolic link   |
| `vim`       | Edit files               |

------

# 💡 Remember

```bash
pwd     → where am I?
ls      → what's here?
cd      → move around
touch   → create a file
mkdir   → create a directory
cat     → read a file
cp      → copy
mv      → move / rename
rm      → delete
ln      → create a hard link
ln -s   → create a soft link
vim     → edit a file
```
