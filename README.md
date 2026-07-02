<div align="center">
  
# PMA
Pollhammer Mail Archive <br>
</div>
<p align="center">
</p>

<br>

## 🛠 Personal Fork & Private Mail Archivee

> This is a personal fork of [Open Archiveer](https://github.com/LogicLabs-OU/OpenArchiveer), created for learning, experimentation, and hobby projects. It is also used as my private email Archiveing solution for my personal domain **"pollhammer.org"**. The focus is on exploring new ideas, testing custom features, and adapting the platform to my individual needs.

---

## System Requirements

- Linux server (recommended: Ubuntu 22.04 LTS or newer)
- Docker (v20+)
- Docker Compose Plugin (v2+)
- Minimum 2 GB RAM (recommended: 4 GB+)
- At least 20 GB free disk space

---

## Installation Guide
### 1. Clone the Repository

Clone this fork directly to your server:

```bash
git clone https://github.com/pollhammer/pma.git
cd pma
```
---
### 2. Prepare Data Directory

Create a local directory for persistent data storage to avoid permission issues:

```bash
sudo mkdir -p /var/data/pma
sudo chown -R $(id -u):$(id -g) /var/data/pma
```
---
### 3. Configuration (.env)

Copy the example environment file and customize your security keys:

```bash
cp .env.example.docker .env
nano .env
```

## Important:
You must change the following values for security reasons:

- POSTGRES_PASSWORD
- MEILI_MASTER_KEY
- ENCRYPTION_KEY
---
### 4. Launch the Containers

Start the Archiveing system using Docker Compose:
```bash
docker compose up -d
```

Check container status:
```bash
docker compose ps
```
---
### 5. Initial Setup

Access the web interface via your browser:
```bash
http://<your-server-ip>:3000
```

Follow the setup wizard to:

- Create your admin account
- Configure your first mail source
- Verify indexing and Archivee synchronization
---
## Updating

To update the system:
```bash
git pull
docker compose pull
docker compose up -d
```

## Screenshots

**Login Page:**
![Login Page](/screenshots/Login_01.png)

**Simple User Interface:**<br>
- A streamlined view for searching, viewing, and saving emails, without unnecessary complexity. ❗CUSTOM❗
![Simple UI](/screenshots/simple%20default%20UI_01.png)

**Default User Role Generator:**<br>
- Generate standard roles using the mailbox ID and the user's email address. ❗NEW❗
![Role Generator](/screenshots/default%20user%20role%20generator_01.png)
