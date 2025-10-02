# 🚀 n8n Docker Installation Guide

This project sets up **n8n** – a powerful workflow automation tool – using **Docker** with authentication and persistent data storage.

---

## 📦 Prerequisites

Make sure the following are installed on your machine:

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

Check installation:

```bash
docker --version
docker compose version


🛠️ Installation Steps
1. Clone or Create Project Directory

mkdir n8n-server && cd n8n-server


2. Create Persistent Data Directory

mkdir n8n-data

3. Set Permissions

chown -R 1000:1000 n8n-data
chmod -R 775 n8n-data

4. Create .env File

Create a .env file with the following contents:

# Basic Auth
N8N_BASIC_AUTH_ACTIVE=true
N8N_BASIC_AUTH_USER=your-username
N8N_BASIC_AUTH_PASSWORD=your-password

# Server Settings
N8N_HOST=your-server-ip
N8N_PORT=5678
N8N_PROTOCOL=http
N8N_SECURE_COOKIE=false

# Environment
NODE_ENV=production

⚠️ Replace your-username, your-password, and your-server-ip with your actual credentials and IP.

5. Create docker-compose.yml

6. Start n8n

Run:

docker compose up -d


7. Access n8n

Open your browser and go to:

http://your-server-ip:5678


✅ Success!

You now have:

🔐 Basic authentication

💾 Persistent data storage

🚀 n8n running in Docker
