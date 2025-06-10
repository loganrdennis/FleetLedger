# 📦 Deployment Details

This document outlines the deployment architecture and configuration for this project.

The application is **self-hosted**, containerized with **Docker**, and deployed on a **privately managed Proxmox VE server** for production-grade control and performance — with zero reliance on third-party SaaS or cloud platforms.

---

## 🧱 Infrastructure Overview

- **Hypervisor:** Proxmox VE 8.x
- **Deployment Target:** Ubuntu 22.04 (running as an LXC container or VM)
- **Stack Orchestration:** Docker + Docker Compose
- **Reverse Proxy & SSL:** NGINX with Let's Encrypt
- **Database:** PostgreSQL (inside Docker)
- **Services:** FastAPI backend, pgAdmin, and optional frontend (React)
- **Security:** Admin-only route protection, HTTPS, backups

> *Each component is chosen to be free, robust, and widely respected in industry hiring.*

---

## 🔧 Stack Components

| Component | Tool | Reason |
|----------|------|--------|
| **Containerization** | Docker | Industry standard, reproducible environments |
| **Orchestration** | Docker Compose | Declarative, readable service wiring |
| **Hypervisor** | Proxmox VE | Powerful open-source virtualization, real-world infra |
| **Database** | PostgreSQL | Most trusted RDBMS for financial apps |
| **Web Server** | NGINX | Lightweight, scalable, widely used in production |
| **SSL Certificates** | Let’s Encrypt + Certbot | Free, automated TLS setup |
| **Database GUI** | pgAdmin | Visual PostgreSQL management (optional) |
| **Backups** | `pg_dump` + `cron` + `rsync` | Automated, scriptable, zero-cost backup flow |

---

## 🌐 Networking

- **HTTPS:** Enforced using Let’s Encrypt via Certbot with auto-renewals
- **Proxy Routing:** NGINX routes external requests to services (e.g. backend on port 8000)
- **Firewall:** Managed via UFW inside the VM/LXC (optional)

---

## 🔐 Security

- JWT authentication with hashed passwords
- Admin-only access routes (e.g. payroll, dashboard)
- Rate limiting and brute force protection (coming soon)
- Encrypted traffic via HTTPS
- Daily encrypted DB backups

---

## 🗃️ Backup Strategy

- Daily `pg_dump` SQL backups via `cron`
- Files written to external mounted volume
- Off-host rsync (to another disk or NAS if available)
- Retention policy: 7 days of rolling backups

---

## 🚀 Deployment Steps (Basic)

1. Clone the repo to your Proxmox-hosted Ubuntu container or VM
2. Copy `.env.example` to `.env` and configure secrets (e.g. JWT secret, DB password)
3. Run:
   ```bash
   docker-compose up -d
