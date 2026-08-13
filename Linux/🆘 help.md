Linux provides several ways to learn how a command works without searching the internet.

The main tools are:

```
help → Bash built-in commands
man  → Detailed documentation
--help → Quick command options
info → Detailed documentation for some commands
whatis → Short description
```

------

# 🆘 `help`

`help` is mainly used for **Bash built-in commands** such as `cd`, `echo`, `alias`, and `export`.

### 🌳 `help`

List available Bash built-in commands:

```bash
help
```

Get help for a command:

```bash
help cd
```

------

### 🌳 `help -d`

Show a short description:

```bash
help -d cd
```

------

### 🌳 `help -s`

Show the command syntax:

```bash
help -s cd
```

------

### 🌳 `help help`

Get information about the `help` command itself:

```bash
help help
```

------

# 📖 `man`

`man` provides detailed documentation for Linux commands.

```bash
man ls
```

Other examples:

```bash
man cp
man mv
man grep
man bash
```

> `man` is especially useful for **external commands** such as `ls`, `cp`, `mv`, `grep`, etc.

------

# ❓ `-help`

Most Linux commands support `--help` for a quick summary.

```bash
ls --help
grep --help
docker --help
```

This is usually faster than reading the full `man` page.

------

# 🔎 `whatis`

Shows a short description of a command:

```bash
whatis ls
whatis grep
whatis date
```

------

# 📚 `info`

`info` provides detailed documentation for some Linux commands:

```bash
info ls
info bash
```

------

# 🧭 Useful `man` Navigation

When a `man` page opens, it is usually displayed using `less`.

| Key       | Action             |
| --------- | ------------------ |
| `↑` / `↓` | Move up/down       |
| `Space`   | Page down          |
| `b`       | Page up            |
| `g`       | Beginning          |
| `G`       | End                |
| `/word`   | Search             |
| `n`       | Next search result |
| `q`       | Exit               |

------

# 🆚 `help` vs `man` vs `-help`

| Tool        | Best For                    |
| ----------- | --------------------------- |
| `help cd`   | Bash built-in commands      |
| `man ls`    | Detailed documentation      |
| `ls --help` | Quick options               |
| `whatis ls` | Short description           |
| `info ls`   | Detailed info documentation |

------

# 🧪 Practice

Try these commands:

```bash
help cd
help -s cd
ls --help
man ls
whatis ls
info ls
```

------

# 🧠 Remember

If you don't know how a command works:

```
Quick answer       → command --help
Bash built-in      → help command
Detailed manual    → man command
Short description  → whatis command
Detailed info      → info command
```

**Tip:** `help` is mainly for Bash built-ins, while `man` is the main reference for external Linux commands.