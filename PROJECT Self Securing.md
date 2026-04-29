# 🛠️ PROJECT: Self-Securing App Gateway

You are an expert full-stack and DevOps engineer.

Your task is to design and build a production-ready "Self-Securing App Gateway" that acts as a reverse proxy, TLS manager, and monitoring dashboard for web applications.

---

## 🎯 OBJECTIVE

Create a system that:

1. Uses Nginx as a reverse proxy
2. Uses Certbot to automatically manage HTTPS certificates
3. Uses FastAPI as a backend control and monitoring API
4. Provides a dashboard to visualize:
   - SSL certificate expiration dates
   - Renewal logs
   - Domain health
   - Active routes

---

## 🧱 TECH STACK

- Backend: FastAPI (Python)
- Reverse Proxy: Nginx
- TLS: Certbot (Let's Encrypt)
- Frontend: React (Vite) OR simple HTML dashboard
- OS: Ubuntu (DigitalOcean droplet target)
- Optional: Docker Compose

---

## 📦 REQUIRED FEATURES

### 1. Nginx Reverse Proxy
- Configure Nginx to:
  - Route `/api` → FastAPI backend
  - Support HTTPS using Certbot certificates
- Include config files and explanation

---

### 2. Certbot Integration
- Install and configure Certbot
- Issue certificates for a domain
- Enable auto-renewal (cron or systemd)
- Document setup steps

---

### 3. FastAPI Backend

Implement the following endpoints:

#### `/certs`
- Return all SSL certificates
- Include:
  - domain name
  - expiration date
  - days remaining

#### `/health`
- Check:
  - domain availability
  - HTTP status
  - latency (optional)

#### `/logs`
- Parse Certbot logs
- Return recent renewal attempts

#### `/alerts`
- Return warnings for:
  - certificates expiring in < 15 days
  - failed renewals

---

### 4. Certificate Parsing
- Read from:
  `/etc/letsencrypt/live/`
- Extract expiration using Python (ssl or OpenSSL)

---

### 5. Dashboard UI

Create a simple dashboard that:
- Fetches data from FastAPI
- Displays:
  - Certificate status (color-coded)
  - Expiration countdown
  - Domain health
- Clean, modern UI (Tailwind preferred)

---

### 6. Logging & Monitoring
- Store logs in a readable format
- Display logs via API
- Handle errors gracefully

---

## 📁 PROJECT STRUCTURE

Provide a clean structure like:

- `/backend` (FastAPI)
- `/frontend` (dashboard)
- `/nginx` (config files)
- `/scripts` (certbot + setup)
- `docker-compose.yml` (optional)

---

## ⚙️ SETUP INSTRUCTIONS

Provide step-by-step setup for:
- Ubuntu server
- Installing Nginx
- Installing Certbot
- Running FastAPI
- Connecting everything together

---

## 🔒 BONUS FEATURES (if possible)

- Basic authentication for dashboard
- Multiple domain support
- Webhook or email alerts
- Dockerized deployment

---

## 🧠 EXPECTATIONS

- Write clean, modular, production-quality code
- Include comments explaining key logic
- Provide all configs (Nginx, systemd, etc.)
- Prioritize clarity and maintainability

---

## 🚀 OUTPUT FORMAT

- Provide:
  1. Full code
  2. Config files
  3. Setup instructions
  4. Explanations where necessary

Build this as if it will be showcased in a professional developer portfolio.
