# Netstat



## What is it?

`netstat` is a network utility used to display network connections, routing tables, and open ports.

## Why use it?

- Check which ports are in use
- Identify running services
- Debug networking issues

## Useful Command

### Show listening ports with process info

```bash
netstat -tulpn
```

## Flags Explained

- `-t` → TCP connections
- `-u` → UDP connections
- `-l` → Listening ports
- `-p` → Show process using port
- `-n` → Show numeric addresses

## Example Output Use Case

Find which service is using port 5432 (Postgres).

