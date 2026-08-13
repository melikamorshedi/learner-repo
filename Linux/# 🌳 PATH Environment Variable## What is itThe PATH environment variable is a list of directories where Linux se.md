# 📄 Linux Environment Variables

## 🌍 What Are Environment Variables?

Environment variables store information used by the shell and programs.

Examples:

```bash
echo "$HOME"
echo "$USER"
echo "$SHELL"
```

A variable uses this format:

```bash
NAME=value
```

> ⚠️ No spaces around `=`.
> 

---

# 👀 Viewing Variables

### 🌳 `echo`

Show a variable:

```bash
echo "$HOME"
```

Without `$`, Bash treats it as normal text:

```bash
echo HOME
```

Output:

```
HOME
```

---

### 🌳 `printenv`

Show all environment variables:

```bash
printenv
```

Show one variable:

```bash
printenv HOME
```

Show multiple:

```bash
printenv HOME USER PATH
```

---

### 🌳 `env`

Show environment variables:

```bash
env
```

---

### 🌳 `set`

Show shell variables, environment variables, and functions:

```bash
set
```

Because the output is large:

```bash
set | less
```

---

# 🆚 Shell Variable vs Environment Variable

### Shell variable

```bash
MY_VAR="hello"
```

Available in the current shell.

### Environment variable

```bash
export MY_VAR="hello"
```

Available to the current shell **and child processes**.

Test it:

```bash
bash -c 'printenv MY_VAR'
```

---

# ➕ Creating Variables

Create a temporary variable:

```bash
XYZ="test"
```

Check it:

```bash
echo "$XYZ"
```

Output:

```
test
```

Export it:

```bash
export XYZ
```

Or do both at once:

```bash
export XYZ="test"
```

---

# 🎯 Variable for One Command

You can set a variable only for one command:

```bash
DEBUG=1 printenv DEBUG
```

After the command finishes:

```bash
echo "$DEBUG"
```

The variable is not set in the current shell.

---

# ➖ Removing Variables

Use `unset`:

```bash
unset XYZ
```

Check:

```bash
printenv XYZ
```

---

# 🛣️ `$PATH`

`PATH` contains directories where Linux searches for executable commands.

View it:

```bash
echo "$PATH"
```

Example:

```
/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin
```

Directories are separated by `:`.

---

## ➕ Add to `$PATH`

### Temporarily

Add to the beginning:

```bash
export PATH="$HOME/bin:$PATH"
```

Add to the end:

```bash
export PATH="$PATH:/opt/bin"
```

The change normally lasts only for the current shell session.

---

# 💾 Make Variables Permanent

For Bash interactive shells:

```bash
nano ~/.bashrc
```

Add:

```bash
export EDITOR="nano"
export MY_VAR="hello"
export PATH="$HOME/bin:$PATH"
```

Reload:

```bash
source ~/.bashrc
```

> `source` applies the changes to the current shell.
> 

---

# 🔐 System-Wide Variables

### `/etc/environment`

Used for system-wide login environment variables.

Example:

```
JAVA_HOME=/usr/lib/jvm/default-java
```

Do **not** use `export` here.

---

### `/etc/profile.d/`

Useful for system-wide shell configuration.

Create a file:

```bash
sudo nano /etc/profile.d/custom.sh
```

Add:

```bash
export APP_ENV="production"
```

This can apply to users when they start a new login shell.

---

# 👤 New User Defaults

`/etc/skel/` contains files copied into the home directory when a new user is created.

```bash
ls /etc/skel/
```

Changes here affect **new users**, not existing users.

---

# 🔢 `SHLVL`

Shows the current Bash shell level:

```bash
echo "$SHLVL"
```

Start another shell:

```bash
bash
```

Check again:

```bash
echo "$SHLVL"
```

Each new Bash subshell increases the value.

---

# 📋 Important Environment Variables

| Variable | Meaning |
| --- | --- |
| `$HOME` | User's home directory |
| `$USER` | Current username |
| `$SHELL` | User's login shell |
| `$PATH` | Command search directories |
| `$PWD` | Current directory |
| `$OLDPWD` | Previous directory |
| `$HOSTNAME` | Computer hostname |
| `$LANG` | System language/locale |
| `$TERM` | Terminal type |
| `$EDITOR` | Default text editor |
| `$UID` | User ID |
| `$PPID` | Parent process ID |
| `$SHLVL` | Bash shell level |
| `$HISTSIZE` | Number of history commands |
| `$HISTFILE` | History file location |
| `$LOGNAME` | Login name |

---

# 🧪 Practice

Create and export a variable:

```bash
export APP_ENV="development"
```

Check it:

```bash
echo "$APP_ENV"
```

Check whether it is exported:

```bash
printenv APP_ENV
```

Open a child shell:

```bash
bash
```

Check again:

```bash
echo "$APP_ENV"
```

Exit:

```bash
exit
```

Remove it:

```bash
unset APP_ENV
```

---

# 📝 Quick Summary

| Task | Command |
| --- | --- |
| Show variable | `echo "$VAR"` |
| Show all environment variables | `env` / `printenv` |
| Show all variables | `set` |
| Create shell variable | `VAR=value` |
| Create environment variable | `export VAR=value` |
| Remove variable | `unset VAR` |
| Temporary variable | `VAR=value command` |
| Add to PATH | `export PATH="$PATH:/dir"` |
| Reload `.bashrc` | `source ~/.bashrc` |
| User configuration | `~/.bashrc` |
| System-wide environment | `/etc/environment` |
| System-wide shell config | `/etc/profile.d/` |
| New-user defaults | `/etc/skel/` |

---

# 🧠 Key Concept

```
Shell Variable
      ↓
export
      ↓
Environment Variable
      ↓
Inherited by child processes
```

The most important difference:

```bash
MY_VAR="hello"
```

⬆️ Current shell only

```bash
export MY_VAR="hello"
```

⬆️ Current shell + child processes
