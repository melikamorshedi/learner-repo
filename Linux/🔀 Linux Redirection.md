# 🔀 Linux Redirection

Redirection lets you send command input or output to a file or another command.

---

# 📥 Standard Input, Output, and Error

Linux commands use three standard data streams:

| Stream   | Number | Meaning               |
| -------- | ------ | --------------------- |
| `stdin`  | `0`    | Input to a command    |
| `stdout` | `1`    | Normal command output |
| `stderr` | `2`    | Error messages        |

By default:

```text
stdin  → keyboard
stdout → terminal
stderr → terminal
```

---

# 📤 Output Redirection `>`

Send command output to a file.

```bash
ls > files.txt
```

This creates `files.txt` if it doesn't exist.

⚠️ If the file already exists, `>` **overwrites its contents**.

---

# ➕ Append Output `>>`

Add output to the end of a file without deleting existing content.

```bash
echo "Hello" >> notes.txt
```

---

# 📥 Input Redirection `<`

Use a file as the input for a command.

```bash
command < file.txt
```

Example:

```bash
tr a-z A-Z < file.txt
```

---

# ❌ Error Redirection `2>`

Save error messages to a file.

```bash
ls something 2> error.txt
```

The normal output and errors are separate:

```text
stdout → terminal
stderr → error.txt
```

---

# 🔀 Redirect Output and Errors Together

Send both normal output and errors to the same file:

```bash
command > output.txt 2>&1
```

A shorter Bash form is:

```bash
command &> output.txt
```

---

# 🔗 Pipe `|`

A pipe sends the output of one command directly to another command.

```bash
command1 | command2
```

Example:

```bash
ls | wc -l
```

Meaning:

```text
ls
 ↓
list of files
 ↓
wc -l
 ↓
number of lines
```

You can connect several commands:

```bash
command1 | command2 | command3
```

---

# 🧪 Simple Practice

Create a file:

```bash
echo "Linux" > names.txt
```

Add another line:

```bash
echo "Docker" >> names.txt
```

Read the file:

```bash
cat names.txt
```

Save the directory listing:

```bash
ls > files.txt
```

Count the files:

```bash
ls | wc -l
```

Create an error:

```bash
ls does-not-exist 2> error.txt
```

Read the error:

```bash
cat error.txt
```

---

# 📝 Quick Reference

| Operator | Purpose                                 |
| -------- | --------------------------------------- |
| `>`      | Write/overwrite output                  |
| `>>`     | Append output                           |
| `<`      | Read input from a file                  |
| `2>`     | Redirect errors                         |
| `2>&1`   | Send errors to the same place as stdout |
| `&>`     | Redirect stdout and stderr              |
| `|`      | Send output to another command          |

---

# 💡 Remember

```bash
>   → put output into a file
>>  → add output to a file
<   → take input from a file
2>  → save errors
|   → send output to another command
```