

------

# 📦 Install Gitea in Docker with Systemd PostgreSQL

## Project Architecture

```
               Browser
                   │
             http://localhost:3000
                   │
         ┌─────────────────────┐
         │   Gitea Container   │
         │ network_mode: host  │
         └──────────┬──────────┘
                    │
            localhost:5432
                    │
      PostgreSQL (Systemd Service)
```

------

# Step 1 — Start PostgreSQL Service

## What is it?

PostgreSQL is running directly on the Linux host as a **Systemd service**, not inside Docker.

## Why use it?

- Keeps the database independent from containers.
- Data remains available even if the Gitea container is removed.
- Common architecture for production environments.

## Useful Commands

Start PostgreSQL

```bash
sudo systemctl start postgresql
```

Check status

```bash
sudo systemctl status postgresql
```

Restart

```bash
sudo systemctl restart postgresql
```

Enable on boot

```bash
sudo systemctl enable postgresql
```

Verify PostgreSQL is listening

```bash
sudo ss -tulpn | grep 5432
```

And, prepare the database inside Postgres using this command:

```bash
su -c "psql" - postgres
```

Inside the PostgreSQL's prompt, write these:

```sql
-- create user gitea with password gitea
CREATE ROLE gitea WITH LOGIN PASSWORD 'gitea';

-- create database giteadb
CREATE DATABASE giteadb WITH OWNER gitea TEMPLATE template0 ENCODING UTF8 LC_COLLATE 'en_US.UTF-8' LC_CTYPE 'en_US.UTF-8';
```





------

# Step 2 — Create the Gitea Project Directory

## What is it?

A directory that stores the Docker Compose file and Gitea persistent data.

## Why use it?

- Keeps project files organized.
- Allows data persistence using Docker volumes.

## Useful Commands

```bash
mkdir -p ~/gitea
cd ~/gitea

mkdir data
```

Verify

```bash
tree
```

Output

```
gitea/
├── data
└── docker-compose.yml
```

------

# Step 3 — Understand Host Networking

## What is it?

Normally Docker creates an isolated bridge network.

Using

```yaml
network_mode: host
```

makes the container use the host's network directly.

```
Container
     │
Host Network
     │
localhost:5432
```

------

## Why use it?

Since PostgreSQL is already installed on the host, Gitea can simply connect to

```
localhost:5432
```

without creating a Docker bridge network.

------

## Useful Commands

List Docker networks

```bash
docker network ls
```

Inspect Host Network

```bash
docker network inspect host
```

------

# Step 4 — Create the Docker Compose File

## What is it?

Docker Compose defines how the Gitea container will run.

## Why use it?

- Easy deployment
- Easy maintenance
- Infrastructure as Code

## Create the file

```bash
nano docker-compose.yml
```

Paste the following:

```yaml
services:
  gitea:
    image: gitea/gitea:latest
    container_name: gitea

    restart: unless-stopped

    network_mode: host # this line, allows the container to access the 'host network'.

    volumes:
      - ./data:/data

    environment:
      USER_UID: 1000
      USER_GID: 1000
```

Notice that there is **no PostgreSQL service** because PostgreSQL is managed by **Systemd**, not Docker.

------

# Step 5 — Start the Gitea Container

## What is it?

Docker Compose downloads the image and creates the Gitea container.

## Why use it?

Starts Gitea using the configuration defined in `docker-compose.yml`.

## Useful Commands

Start

```bash
docker compose up -d
```

Show running containers

```bash
docker ps
```

View logs

```bash
docker compose logs -f
```

Stop

```bash
docker compose down
```

Restart

```bash
docker compose restart
```

------

# Step 6 — Open the Gitea Installer

## What is it?

When Gitea starts for the first time, it launches a web-based installation wizard.

## Why use it?

This wizard configures the database connection and initializes the application.

Open your browser:

```
http://localhost:3000
```

or

```
http://<SERVER_IP>:3000
```

------

# Step 7 — Configure the Database

## What is it?

Gitea needs to connect to the PostgreSQL database running on the host machine.

## Why use it?

Without a database, Gitea cannot store repositories, users, or settings.

Use the following values:

| Setting       | Value                    |
| ------------- | ------------------------ |
| Database Type | PostgreSQL               |
| Host          | localhost:5432           |
| Username      | gitea                    |
| Password      | Your PostgreSQL Password |
| Database Name | gitea                    |

Click

```
Install Gitea
```

------

# Project Structure

```
gitea/
├── data/
└── docker-compose.yml
```

------

# Useful Docker Commands

```bash
docker compose up -d

docker compose down

docker compose restart

docker compose logs -f

docker ps

docker images
```

------

## Why This Setup?

- ✅ Gitea runs inside a Docker container.
- ✅ PostgreSQL runs as a native Systemd service on the host.
- ✅ `network_mode: host` allows Gitea to connect to PostgreSQL through `localhost:5432`.
- ✅ The database is managed independently of the container, simplifying upgrades, backups, and data persistence.

------

- 