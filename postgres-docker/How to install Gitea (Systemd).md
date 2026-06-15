# How to install Gitea (Systemd)

To install Gitea, we should:

1. Download and install Gitea from binary using the link below:

   https://docs.gitea.com/installation/install-from-binary

2. Install Postgresql using APT. Use this link:
   https://docs.gitea.com/installation/database-prep

## Download and install Gitea from binary

1. Download Gitea's binary file using wget
   ```bash
   wget -O gitea https://dl.gitea.com/gitea/1.26.2/gitea-1.26.2-linux-amd64
   chmod +x gitea
   ```

2. Make sure Git is installed. Check git version

   ```bash
   git --version
   ```

3. Create gitea user
   ```bash
   # On Ubuntu/Debian:
   adduser \
      --system \
      --shell /bin/bash \
      --gecos 'Git Version Control' \
      --group \
      --disabled-password \
      --home /home/git \
      git
   ```

4. Create gitea's folders and configure permissions:

   ```bash
   mkdir -p /var/lib/gitea/{custom,data,log}
   chown -R git:git /var/lib/gitea/
   chmod -R 750 /var/lib/gitea/
   mkdir /etc/gitea
   chown root:git /etc/gitea
   chmod 770 /etc/gitea
   ```

   

5. Copy the Gitea binary to a global location
   ```bash
   cp gitea /usr/local/bin/gitea
   ```

6. Creating a Systemd service file to start Gitea automatically

   - Create a service file
     ```bash
     sudo nano /etc/systemd/system/gitea.service
     ```

   - Paste the following into the file:

     ```bash
     [Unit]
     Description=Gitea
     After=network.target
     
     [Service]
     RestartSec=2s
     Type=simple
     User=git
     Group=git
     WorkingDirectory=/var/lib/gitea/
     ExecStart=/usr/local/bin/gitea web --config /etc/gitea/app.ini
     Restart=always
     Environment=USER=git HOME=/home/git GITEA_WORK_DIR=/var/lib/gitea
     
     [Install]
     WantedBy=multi-user.target
     ```

   -  Restart Systemd daemon

     ```bash
     sudo systemctl daemon-reload
     ```

   - Start the service and enable it:

     ```bash
     sudo systemctl enable gitea.service
     sudo systemctl start gitea.service
     ```



## Install Postgresql using APT and configure it for Gitea

1. Install Postgresql-16 using APT

   ```bash
   sudo apt update
   sudo apt install postgresql-16
   ```

2. On the database server, login to the database console as superuser:

   ```bash
   su -c "psql" - postgres
   ```

3. Insider Postgresql's psql prompt, type these:

   ```postgresql
   -- Create user gitea
   CREATE ROLE gitea WITH LOGIN PASSWORD 'gitea';
   
   
   -- Create database giteadb
   CREATE DATABASE giteadb WITH OWNER gitea TEMPLATE template0 ENCODING UTF8 LC_COLLATE 'en_US.UTF-8' LC_CTYPE 'en_US.UTF-8';
   ```

   

## Open Gitea and finish installation using the install wizard

1. Open `http://127.0.0.1:3000`

2. Enter these parameters:

   - Database Type: `Postgresql`

   - Database username: `gitea`
   - Database Password: `gitea`
   - Database Name: `giteadb`

3. Click next

4. Done✅