# 🚀 Gitea Installation with Docker + PostgreSQL (Systemd) + Host Networking

------

# 🧩 What are we building?

We will set up:

- Gitea (Git server)
- PostgreSQL (database backend)
- Docker (runtime)
- Systemd-managed containers (auto-start on boot)
- Docker **host networking mode**

------

# ⚙️ Step 1: Install Docker

## Update system

```bash
sudo apt update && sudo apt upgrade -y
```

## Install Docker

```bash
sudo apt install docker.io -y
```

## Enable and start Docker

```bash
sudo systemctl enable docker
sudo systemctl start docker
```

## Verify

```bash
docker --version
```

------

# 🗄️ Step 2: Create Docker Network (Host Mode Concept)

We will use **host networking**, so no custom bridge network is needed.

------

# 🌐 What is Host Networking in Docker?

## 📌 Definition

**Host networking mode** means:

> The container uses the **host machine’s network directly** (no NAT, no port mapping).

------

## ❓ Why use it?

- Better performance (no network translation)
- Easier debugging (localhost = container)
- Required for some system-level services
- Useful for databases and internal tools

------

## ⚠️ Important Notes

- No `-p` port mapping needed
- Ports inside container = ports on host
- Risk: port conflicts with host services

------

## 🧪 Example

Instead of:

```bash
docker run -p 3000:3000 gitea/gitea
```

We use:

```bash
docker run --network host gitea/gitea
```

------

## 🔧 Useful Commands

### Run container with host network

```bash
docker run --network host <image>
```

### Inspect container network

```bash
docker inspect <container>
```

### List networks

```bash
docker network ls
```

------

# 🐘 Step 3: Run PostgreSQL (Systemd + Docker)

## Pull PostgreSQL image

```bash
docker pull postgres:16
```

## Run PostgreSQL (Host Network)

```bash
docker run -d \
  --name postgres \
  --network host \
  -e POSTGRES_USER=gitea \
  -e POSTGRES_PASSWORD=strongpassword \
  -e POSTGRES_DB=gitea \
  -v /opt/postgres-data:/var/lib/postgresql/data \
  postgres:16
```

------

## Check container

```bash
docker ps
```

------

# 🧠 Step 4: Run Gitea Container

## Pull Gitea image

```bash
docker pull gitea/gitea:latest
```

## Run Gitea (Host Network)

```bash
docker run -d \
  --name gitea \
  --network host \
  -e USER_UID=1000 \
  -e USER_GID=1000 \
  -e DB_TYPE=postgres \
  -e DB_HOST=127.0.0.1:5432 \
  -e DB_NAME=gitea \
  -e DB_USER=gitea \
  -e DB_PASSWD=strongpassword \
  -v /opt/gitea:/data \
  gitea/gitea:latest
```

------

# 🔍 Step 5: Access Gitea

Open browser:

```
http://localhost:3000
```

(or your server IP)

------

# ⚙️ Step 6: Create Systemd Service (Auto Start)

## Create service file

```bash
sudo nano /etc/systemd/system/gitea.service
```

## Add:

```ini
[Unit]
Description=Gitea Container
After=network.target docker.service
Requires=docker.service

[Service]
Restart=always
ExecStart=/usr/bin/docker start -a gitea
ExecStop=/usr/bin/docker stop -t 2 gitea

[Install]
WantedBy=multi-user.target
```

------

## Enable service

```bash
sudo systemctl daemon-reload
sudo systemctl enable gitea
sudo systemctl start gitea
```

------

## Check status

```bash
sudo systemctl status gitea
```

------

# 🧪 Step 7: Useful Debug Commands

## Check logs

```bash
docker logs gitea
docker logs postgres
```

## Restart containers

```bash
docker restart gitea
docker restart postgres
```

## Stop containers

```bash
docker stop gitea postgres
```

------



