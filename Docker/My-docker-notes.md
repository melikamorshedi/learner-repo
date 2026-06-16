## My docker notes

### How to set DNS in linux (commandline-based)

1. Simple way, but might be overwritten

   ````bash
   sudo nano /etc/resolv.conf
   ````

   - **comment everything** and add this to the end of the file:

   ```
   nameserver 8.8.8.8 # Google's DNS
   ```

2. Better, permanent way, using *resolvectl*:

   ```bash
   sudo resolvectl dns ens34 8.8.8.8 8.8.4.4
   ```

   

### How to use mirrors in docker

- To use mirrors in **adhoc** **mode**

  ```bash
  docker pull docker.devneeds.ir/postgres:16
  ```

- To set mirrors **system-wide**, create a file in */etc/docker/daemon.json* and put the following inside:

  ```bash
  sudo nano /etc/docker/daemon.json
  ```

  ```json
  {
    "registry-mirrors": 
      "http://docker.devneeds.ir/"
    ]
  }
  ```

- After that, restart docker and its daemon:

  ```bash
  # ریلود کانفیگ
  sudo systemctl daemon-reload
  
  # ریستارت Docker
  sudo systemctl restart docker
  
  ```

  

### How to execute a command inside of a docker container

```bash
# to get a BASH shell
docker exec -it my-postgres-container-1 bash

# to get a simple shell
docker exec -it my-postgres-container-1 sh

# to get a directory listing
docker exec my-postgres-container-1 ls

```

### How to see the list of permisions

```bash
ls -l
# or the shorthand one in ubuntu
ll
```

