# Working with Files





# 1. 📁 Files in Linux Command Line

## What is it?

In Linux, almost everything is represented as a **file**. Files are organized inside **directories**, forming a hierarchical filesystem.

The command line provides several commands for creating, viewing, modifying, copying, moving, and deleting files.

> ------
>
> ## 📂 Basic File Commands
>
> | Command | Purpose                    |
> | ------- | -------------------------- |
> | `pwd`   | Show current directory     |
> | `ls`    | List files and directories |
> | `cd`    | Change directory           |
> | `touch` | Create an empty file       |
> | `cat`   | Display file contents      |
> | `less`  | View a file page by page   |
> | `mkdir` | Create a directory         |
> | `rm`    | Remove files               |
> | `rmdir` | Remove empty directories   |
>
> ### Examples
>
> ```bash
> pwd
> ```
>
> Shows your current location.
>
> ```bash
> ls
> ```
>
> Lists files and directories.
>
> ```bash
> touch notes.txt
> ```
>
> Creates an empty file.
>
> ```bash
> mkdir projects
> ```
>
> Creates a directory.
>
> ```bash
> cat notes.txt
> ```
>
> Displays the contents of a file.
>
> ------
>
> ## 👀 Useful `ls` Options
>
> ```bash
> ls -l
> ```
>
> Shows detailed information.
>
> ```bash
> ls -a
> ```
>
> Shows hidden files.
>
> ```bash
> ls -la
> ```
>
> Shows detailed information including hidden files.
>
> ------
>
> ## 🗑️ Removing Files
>
> ```bash
> rm file.txt
> ```
>
> Remove a file.
>
> ```bash
> rm -r directory/
> ```
>
> Remove a directory and its contents.
>
> ⚠️ `rm` normally does not send files to a recycle bin. Be careful.
>
> ------
>
> ## 💡 Key Idea
>
> The basic Linux filesystem workflow is:
>
> ```text
> Navigate → Create → Read → Modify → Copy/Move → Delete
> ```
>
> ------
>
> # 2. 📋 `cp` and `mv` Commands in Linux
>
> ## What are they?
>
> Two fundamental commands for managing files and directories are:
>
> ```bash
> cp
> ```
>
> **Copy** files or directories.
>
> ```bash
> mv
> ```
>
> **Move or rename** files and directories.
>
> ------
>
> ## 📋 `cp` — Copy
>
> ### Basic syntax
>
> ```bash
> cp SOURCE DESTINATION
> ```
>
> ### Copy a file
>
> ```bash
> cp file.txt backup.txt
> ```
>
> Creates `backup.txt` while keeping the original.
>
> ### Copy to another directory
>
> ```bash
> cp file.txt /home/user/Documents/
> ```
>
> ### Copy multiple files
>
> ```bash
> cp file1.txt file2.txt Documents/
> ```
>
> ### Copy a directory
>
> Use `-r`:
>
> ```bash
> cp -r project/ backup/
> ```
>
> ------
>
> ## 🚚 `mv` — Move or Rename
>
> ### Rename a file
>
> ```bash
> mv old.txt new.txt
> ```
>
> ### Move a file
>
> ```bash
> mv file.txt Documents/
> ```
>
> ### Move and rename
>
> ```bash
> mv file.txt Documents/report.txt
> ```
>
> ------
>
> ## ⚙️ Useful Options
>
> ```bash
> cp -i file.txt backup.txt
> ```
>
> Ask before overwriting.
>
> ```bash
> cp -v file.txt backup.txt
> ```
>
> Show what is being copied.
>
> ```bash
> mv -i file.txt backup.txt
> ```
>
> Ask before overwriting.
>
> ```bash
> mv -v file.txt Documents/
> ```
>
> Show the operation.
>
> ------
>
> ## 💡 Key Difference
>
> ```text
> cp → creates another copy
> mv → changes the file's location/name
> ```
>
> ------
>
> # 3. 📝 Vim — Terminal Text Editor
>
> ## What is Vim?
>
> **Vim** is a powerful terminal-based text editor commonly available on Linux systems.
>
> It can be used to:
>
> - Edit configuration files
> - Write scripts
> - Modify source code
> - Edit text files directly from the terminal
>
> ------
>
> ## 🚀 Open or Create a File
>
> ```bash
> vim file.txt
> ```
>
> If the file does not exist, Vim can create it when you save.
>
> ------
>
> ## ⌨️ Vim Modes
>
> Vim is **modal**, meaning different modes perform different operations.
>
> ### Normal Mode
>
> Used for navigation and commands.
>
> Press:
>
> ```text
> Esc
> ```
>
> to return to Normal Mode.
>
> ### Insert Mode
>
> Used to type text.
>
> Press:
>
> ```text
> i
> ```
>
> to start inserting text.
>
> ### Command Mode
>
> Used for commands such as saving and quitting.
>
> From Normal Mode, press:
>
> ```text
> :
> ```
>
> ------
>
> ## 💾 Save and Exit
>
> From Normal Mode:
>
> ```text
> :w
> ```
>
> Save.
>
> ```text
> :q
> ```
>
> Quit.
>
> ```text
> :wq
> ```
>
> Save and quit.
>
> ```text
> :q!
> ```
>
> Quit without saving.
>
> ------
>
> ## ✂️ Basic Editing
>
> From Normal Mode:
>
> ```text
> dd
> ```
>
> Delete a line.
>
> ```text
> yy
> ```
>
> Copy a line.
>
> ```text
> p
> ```
>
> Paste.
>
> ```text
> u
> ```
>
> Undo.
>
> ```text
> Ctrl + r
> ```
>
> Redo.
>
> ------
>
> ## 🔎 Search
>
> From Normal Mode:
>
> ```text
> /word
> ```
>
> Search for `word`.
>
> Press:
>
> ```text
> n
> ```
>
> to go to the next match.
>
> ------
>
> ## 💡 Essential Vim Workflow
>
> ```text
> vim file.txt
>       ↓
>     i → Insert Mode
>       ↓
>   Type/Edit
>       ↓
>    Esc → Normal Mode
>       ↓
>   :wq → Save & Exit
> ```
>
> ⚠️ The most important thing for beginners: **when unsure, press `Esc`** to return to Normal Mode.
>
> ------
>
> # 4. 🛠️ Basic File Operations
>
> This combines the fundamental operations without repeating the commands already covered above.
>
> ## 📌 Create
>
> Create an empty file:
>
> ```bash
> touch file.txt
> ```
>
> Create a directory:
>
> ```bash
> mkdir project
> ```
>
> Create nested directories:
>
> ```bash
> mkdir -p project/src/config
> ```
>
> ------
>
> ## 👁️ View
>
> List files:
>
> ```bash
> ls
> ```
>
> Detailed listing:
>
> ```bash
> ls -l
> ```
>
> Read a small file:
>
> ```bash
> cat file.txt
> ```
>
> Read a large file interactively:
>
> ```bash
> less file.txt
> ```
>
> ------
>
> ## ✏️ Edit
>
> Using Vim:
>
> ```bash
> vim file.txt
> ```
>
> Or Nano:
>
> ```bash
> nano file.txt
> ```
>
> ------
>
> ## 📋 Copy
>
> ```bash
> cp file.txt backup.txt
> ```
>
> Copy a directory:
>
> ```bash
> cp -r project/ project-backup/
> ```
>
> ------
>
> ## 🚚 Move / Rename
>
> Rename:
>
> ```bash
> mv old.txt new.txt
> ```
>
> Move:
>
> ```bash
> mv file.txt Documents/
> ```
>
> ------
>
> ## 🗑️ Delete
>
> Delete a file:
>
> ```bash
> rm file.txt
> ```
>
> Delete an empty directory:
>
> ```bash
> rmdir empty-dir/
> ```
>
> Delete a directory and its contents:
>
> ```bash
> rm -r project/
> ```
>
> ⚠️ Use `rm -r` carefully.
>
> ------
>
> ## 🔗 Links
>
> Create a symbolic link:
>
> ```bash
> ln -s file.txt link.txt
> ```
>
> Create a hard link:
>
> ```bash
> ln file.txt hard-link.txt
> ```
>
> Check inode numbers:
>
> ```bash
> ls -li
> ```
>
> ------
>
> # 🧠 Quick Linux File Reference
>
> ```text
> 📁 Navigation
>    pwd        → current directory
>    ls         → list contents
>    cd         → change directory
> 
> 📄 Creation
>    touch      → create file
>    mkdir      → create directory
> 
> 👁️ Reading
>    cat        → display file
>    less       → view file interactively
> 
> ✏️ Editing
>    vim        → edit with Vim
>    nano       → edit with Nano
> 
> 📋 Management
>    cp         → copy
>    mv         → move / rename
> 
> 🗑️ Deletion
>    rm         → remove file
>    rmdir      → remove empty directory
> 
> 🔗 Links
>    ln         → hard link
>    ln -s      → symbolic link
> ```
>
> ### 🔑 Core Concept
>
> Most everyday Linux file management can be understood as:
>
> **Navigate → Create → Read → Edit → Copy/Move → Link → Delete**.