# Install Gitea using Docker COmpose (With postgres in docker mode)



### 1 — Create a project directory

```bash
mkdir ~/gitea-server
cd ~/gitea-server
```

- Check:

```bash
pwd
```

- You should see something like

```bash
/home/melika/gitea-server
```



### 2 — Create folders for persistent data

```bash
mkdir -p data/gitea
mkdir -p data/postgres
```

- Verify

  ```bash
  tree
  ```

- If `tree` is not installed 

  ```bash
  If tree is not installed
  ```

  

### 3 — Create docker-compose.yml

- Open Nano

  ```bash
  nano docker-compose.yml
  ```

- Paste this exactly.

  ```bash
  version: "3.9"
  
  services:
  
    postgres:
      image: postgres:16
      container_name: postgres
  
      restart: always
  
      environment:
        POSTGRES_USER: gitea
        POSTGRES_PASSWORD: gitea123
        POSTGRES_DB: gitea
  
      volumes:
        - ./data/postgres:/var/lib/postgresql/data
  
      ports:
        - "5432:5432"
  
      networks:
        - gitea-network
  
  
    gitea:
      image: gitea/gitea:latest
      container_name: gitea
  
      restart: always
  
      depends_on:
        - postgres
  
      environment:
        USER_UID: 1000
        USER_GID: 1000
  
        GITEA__database__DB_TYPE: postgres
        GITEA__database__HOST: postgres:5432
        GITEA__database__NAME: gitea
        GITEA__database__USER: gitea
        GITEA__database__PASSWD: gitea123
  
      volumes:
        - ./data/gitea:/data
  
      ports:
        - "3000:3000"
        - "2222:22"
  
      networks:
        - gitea-network
  
  
  networks:
    gitea-network:
  ```

  

### 4 — Check the YAML

- Run

  ```bash
  cat docker-compose.yml
  ```



### 5 — Pull the images

```bash
docker compose pull
```



### 6 — Start everything

```bash
docker compose up -d
```



### 7 — Verify the containers

```bash
docker ps
```



### 8 — Check the logs

- postgres

```bash
docker logs postgres
```

- Gitea

  ```bash
  docker logs gitea
  ```

  



### 9 — Open Gitea

- Open your browser:

  ```bash
  http://localhost:3000
  ```

  









### Useful Docker Compose commands

- Start:

  ```
  docker compose up -d
  ```

- Stop:

  ```
  docker compose stop
  ```

- Restart:

  ```
  docker compose restart
  ```

- View logs:

  ```bash
  docker compose logs -f
  ```

- Check running containers:

  ```bash
  docker compose ps
  ```

- Remove containers (keep your data):

  ```bash
  docker compose down
  ```

- Remove containers **and** the bind-mounted data (be careful):

  ```bash
  rm -rf data
  ```

  