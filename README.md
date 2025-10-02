🚀 n8n Installation Guide (Docker)

This guide helps you set up n8n
 – a powerful workflow automation tool – using Docker in a few simple steps.

📦 Prerequisites

Install Docker
 and Docker Compose
 on your machine.

🛠️ Installation Steps
1. Install Docker

Make sure Docker is installed and running:

docker --version
docker compose version


If not installed, follow the Docker installation guide
.

2. Create Project Directory

Create a directory to host the n8n project:

mkdir n8n-server && cd n8n-server

3. Create a Persistent Data Directory

To ensure data persists across container restarts, create a separate volume directory:

mkdir n8n-data

4. Set Correct Permissions

Grant the required permissions so that the container can access and modify the volume:

chown -R 1000:1000 n8n-data
chmod -R 775 n8n-data

5. Create the .env File

Create a .env file in the n8n-server directory with the following content:

# n8n Configuration
N8N_BASIC_AUTH_ACTIVE=true
N8N_BASIC_AUTH_USER=Your-User
N8N_BASIC_AUTH_PASSWORD=Your-Password
N8N_HOST=Your-IP-Server
N8N_PORT=5678
N8N_PROTOCOL=http
N8N_SECURE_COOKIE=false  # Temporarily disable secure cookie to avoid HTTP access issues
NODE_ENV=production


🔐 Important: Replace Your-User, Your-Password, and Your-IP-Server with your actual credentials and server IP.


6. Create docker-compose.yml

In the same directory, create a file named docker-compose.yml and paste your Docker configuration inside.


7. Start n8n

Launch the container with Docker Compose:

docker compose up -d


Once the container is running, access the n8n interface in your browser:

http://Your-IP-Server:5678

✅ Done!

You now have n8n running via Docker with authentication and persistent storage.
