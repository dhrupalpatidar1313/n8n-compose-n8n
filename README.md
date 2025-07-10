# 🧩 n8n Docker Compose Setup

This repository provides a complete Docker Compose setup to run [n8n](https://n8n.io/), a powerful workflow automation tool, with:

- 🔄 Persistent PostgreSQL backend
- 🔐 Basic authentication
- 🌐 Traefik reverse proxy (optional)
- 📁 Volume storage for data durability

---

## 📦 Stack Components

| Service     | Purpose                         |
|-------------|----------------------------------|
| `n8n`       | Node-based workflow automation   |
| `postgres`  | Persistent database for n8n      |
| `traefik`   | (Optional) Reverse proxy with SSL|

---

## 🚀 Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/dhrupalpatidar1313/n8n-compose-n8n.git
cd n8n-compose-n8n
```

### 2. Setup Environment Variables

Copy and update:

```bash
cp .env.example .env
```

Update values for:

```env
N8N_BASIC_AUTH_USER=admin
N8N_BASIC_AUTH_PASSWORD=your_secure_password
POSTGRES_USER=n8n
POSTGRES_PASSWORD=postgres
N8N_PORT=5678
```

### 3. Start the Services

```bash
docker compose up -d
```

Then visit: [http://localhost:5678](http://localhost:5678)  
Or your domain if Traefik is configured.

---

## 📁 Project Structure

```plaintext
n8n-compose-n8n/
├── .env                # Environment config
├── docker-compose.yml  # Main stack file
├── local-files/        # Persisted n8n data
├── n8n-custom/         # Custom Dockerfile (if any)
│   └── Dockerfile
```

---

## 📦 Docker Image

This project is based on the public Docker image:  
👉 [**Docker Hub: dhrupalpatidar1313/n8n-compose-n8n**](https://hub.docker.com/r/dhrupalpatidar1313/n8n-compose-n8n)

---

## 👤 Maintainer

Built by [Dhrupal Patidar](mailto:dhrupalpatidar1313@gmail.com)  
Contributions and feedback are welcome.

---

## 🪪 License

MIT License © 2025
