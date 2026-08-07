# Linux Directory Structure Explained for Beginners



![Linux Directory Structure](https://linuxhandbook.com/content/images/2020/06/linux-directory-structure.png)Linux Directory 



<iframe srcdoc="<!DOCTYPE html>" innerref="[object Object]" frameborder="0" title="comments-frame" style="box-sizing: border-box; border: 0px solid oklch(0.929 0.013 255.508); margin: 0px; padding: 0px; vertical-align: middle; display: block; color-scheme: normal; width: 392px; height: 152px;"></iframe

------

# 🌳 Linux Directory Structure

## What is it?

Linux organizes all files and directories into a single hierarchical tree.

Everything starts from the **root directory (`/`)** and every file or folder is located somewhere beneath it.

Example:

```text
/
├── bin
├── boot
├── dev
├── etc
├── home
│   └── melika
├── lib
├── media
├── mnt
├── opt
├── proc
├── root
├── sbin
├── srv
├── tmp
├── usr
└── var
```

------

# 📂 `/` — Root Directory

## What is it?

The root directory is the **top-level directory** of the Linux filesystem.

Everything in Linux starts from `/`.

## Why is it important?

- Parent of every file and directory
- Used in absolute file paths

### Example

```bash
/home/melika/Documents
```

This path means:

```
/
└── home
    └── melika
        └── Documents
```

> ⚠️ Don't confuse **`/` (root directory)** with **`/root` (root user's home directory).**

------

# 📂 `/home` — User Home Directories

## What is it?

Stores personal files for each user.

## Why use it?

- Documents
- Downloads
- Pictures
- User-specific settings

### Example

```text
/home/melika
/home/alice
/home/bob
```

------

# 📂 `/root` — Root User's Home

## What is it?

Home directory of the **root (administrator)** user.

Unlike normal users, root's home is **not** inside `/home`.

### Example

```text
/root
```

------

# 📂 `/bin` — Essential User Commands

## What is it?

Contains essential executable programs used by all users.

### Common commands

```text
ls
cp
mv
cat
pwd
mkdir
rm
```

------

# 📂 `/sbin` — System Administration Commands

## What is it?

Contains essential commands used mainly by the system administrator.

### Examples

```text
fsck
reboot
shutdown
ip
```

------

# 📂 `/etc` — Configuration Files

## What is it?

Stores system configuration files.

Whenever you configure Linux, you'll often edit files here.

### Examples

```text
/etc/hostname
/etc/hosts
/etc/passwd
```

------

# 📂 `/usr` — User Programs & Libraries

## What is it?

Contains most installed applications and shared resources.

### Common subdirectories

```text
/usr/bin
/usr/sbin
/usr/lib
/usr/share
```

------

# 📂 `/lib` — Shared Libraries

## What is it?

Contains shared libraries required by programs in `/bin` and `/sbin`.

Think of libraries as reusable code that programs depend on.

------

# 📂 `/var` — Variable Data

## What is it?

Stores files that change while the system is running.

### Examples

- Logs
- Cache
- Mail
- Databases

Common directory:

```text
/var/log
```

------

# 📂 `/tmp` — Temporary Files

## What is it?

Stores temporary files created by programs.

### Note

Files in `/tmp` may be deleted automatically after a reboot.

------

# 📂 `/boot` — Boot Files

## What is it?

Contains files required to start Linux.

Examples include:

- Linux kernel
- GRUB bootloader files

------

# 📂 `/dev` — Device Files

## What is it?

Represents hardware devices as files.

### Common examples

```text
/dev/null
/dev/sda
/dev/random
```

------

# 📂 `/proc` — Process Information

## What is it?

A virtual filesystem that provides information about:

- Running processes
- CPU
- Memory
- Kernel

### Useful files

```text
/proc/cpuinfo
/proc/meminfo
```

------

# 📂 `/media` — Removable Devices

## What is it?

Automatically mounts removable devices.

### Examples

- USB flash drives
- External hard drives
- SD cards

------

# 📂 `/mnt` — Temporary Mount Point

## What is it?

Used for manually mounting filesystems.

Often used by administrators.

------

# 📂 `/opt` — Optional Software

## What is it?

Stores third-party applications that aren't part of the default Linux installation.

Example:

```text
/opt/google
/opt/zoom
```

------

# 📂 `/srv` — Service Data

## What is it?

Stores data served by system services.

Example:

```text
/srv/www
```

------

# ⚠️ Important Safety Tip

Never run the following command:

```bash
sudo rm -rf /
```

This command recursively deletes everything under the root directory and can destroy your Linux installation.

------

# 📋 Summary

| Directory | Purpose                               |
| --------- | ------------------------------------- |
| `/`       | Root of the filesystem                |
| `/home`   | User home directories                 |
| `/root`   | Root user's home                      |
| `/bin`    | Essential user commands               |
| `/sbin`   | System administration commands        |
| `/etc`    | Configuration files                   |
| `/usr`    | Applications and shared resources     |
| `/lib`    | Shared libraries                      |
| `/var`    | Logs, cache, databases                |
| `/tmp`    | Temporary files                       |
| `/boot`   | Bootloader and kernel                 |
| `/dev`    | Device files                          |
| `/proc`   | Process and kernel information        |
| `/media`  | Automatically mounted removable media |
| `/mnt`    | Manual mount point                    |
| `/opt`    | Third-party software                  |
| `/srv`    | Service data                          |











