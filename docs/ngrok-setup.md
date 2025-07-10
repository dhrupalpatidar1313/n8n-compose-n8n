# 🌐 Exposing n8n with Ngrok

This guide shows how to expose your local `n8n` Docker setup to the internet using [Ngrok](https://ngrok.com/), which is useful for:

- Testing **webhooks** in development
- Sharing your n8n UI temporarily with external users
- Avoiding public deployment just for testing

---

## ✅ Prerequisites

- Docker + Docker Compose is running
- Your `n8n` instance is accessible on `http://localhost:5678`
- You have [Ngrok installed](https://ngrok.com/download)

---

## 🚀 Step-by-Step Setup

### 1. Start your n8n stack

```bash
docker compose up -d
```

Make sure n8n is running locally at:

```
http://localhost:5678
```

---

### 2. Run Ngrok to expose your n8n port

```bash
ngrok http 5678
```

You'll see a public forwarding URL like:

```
Forwarding    https://random-subdomain.ngrok.io → http://localhost:5678
```

Copy that `https://...ngrok.io` link.

---

### 3. Update `.env` (Optional)

To persist the public URL in n8n and avoid issues with callback/webhook handling:

```env
N8N_HOST=random-subdomain.ngrok.io
WEBHOOK_URL=https://random-subdomain.ngrok.io/
```

Then restart:

```bash
docker compose down
docker compose up -d
```

---

### 🔐 Auth Tip

If you are using **Basic Auth**, Ngrok will prompt users for username/password set in your `.env`:

```env
N8N_BASIC_AUTH_USER=admin
N8N_BASIC_AUTH_PASSWORD=securepassword
```

---

## 🧠 Bonus: Use Authtoken for Persistent Ngrok Subdomain

1. Sign up at [ngrok.com](https://ngrok.com/)
2. Get your auth token from your dashboard
3. Connect your agent:

```bash
ngrok config add-authtoken <your-token>
```

4. Run with a fixed subdomain (Pro account):

```bash
ngrok http --region=us --subdomain=my-n8n-demo 5678
```

---

## 🛑 Caution

- Ngrok links reset on each run (unless you're a paid user with reserved domains)
- Don’t expose sensitive workflows without proper auth

---

## 📦 Summary

| Command | Purpose |
|--------|---------|
| `ngrok http 5678` | Start tunneling your local n8n |
| `.env update`     | Set webhook/public host config |
| `ngrok config`    | Persist auth token and setup |

---

Happy Automating! ⚙️
