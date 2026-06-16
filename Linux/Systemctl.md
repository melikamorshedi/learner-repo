# ⚙️ systemctl (Systemd Service Manager)

## What is it?

`systemctl` is used to manage system services in Linux.

## Why use it?

- Control services (start/stop/restart)
- Enable services on boot
- Check service status

## Useful Commands

### Start service

```bash
sudo systemctl start <service>
```

### Stop service

```bash
sudo systemctl stop <service>
```

### Restart service

```bash
sudo systemctl restart <service>
```

### Enable on boot

```bash
sudo systemctl enable <service>
```

### Disable on boot

```bash
sudo systemctl disable <service>
```

### Check status

```bash
sudo systemctl status <service>
```