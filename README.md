# Odometra

**A self-hosted accounting system for small trucking companies.**  Custom-built to manage invoicing, payroll, expenses, and financial reporting - with full local control, no SaaS fees, and zero vendor lock-in.

---

### Key Features

- **Invoicing system** tailored for freight and mileage billing
- **Expense tracking** for fuel, maintenance, tolls, etc.
- **Driver payroll** generation with support for bonuses, mileage rates, overtime
- **PDF export** of invoices and pay stubs
- **Self-hosted** via Docker, PostgreSQL, and FastAPI
- **Secure authentication** with JWT
- Built with **React + Tailwind** for a responsive frontend

  ---

  ### Screenshots

  > *(Coming soon)*
  UI previews will be added here as the frontend is developed

  ---

  ### Tech Stack

  | Layer | Technology |
  |-------|------------|
  | Backend | Python, FastAPI |
  | Frontend | React, Tailwind CSS |
  | Database | PostgreSQL |
  | Auth | JWT, bcrypt |
  | Deployment | Docker, NGINX, Proxmox, Let's Encrypt |

  ---

  ### Project Scope

  Odometra is a purpose-built project designed to replace SaaS tools like Quickbooks in a niche use case - owner-operated trucking companies.  It is:

  - Built from scratch without third-party SaaS integrations
  - Designed to demonstrate full-stack infrastructure skills
  - A real-world use case from a real business
  - Fully documented, versioned, and tested for production-readiness
 
  ---

  ### License

  This codebase is made publicly available for educational and portfolio review purposes only.  No license is granted for use, modification, redistribution, or commercial deployment.

  **© 2025 Logan R. Dennis.  All rights reserved.**

  ---

  ## Roadmap

  This project is being built step-by-step with a strong backend-first, infrastructure-oriented approach.  All financial logic is implemented manually - no third-party SaaS services (e.g., Gusto, Stripe) are used.

  ---

  ### Core Architecture
  - [x] Project initialized and documented
  - [ ] Dokcerized backend + PostgreSQL setup
  - [ ] Backend API scaffolded with FastAPI
  - [ ] Database schema for customers, drivers, loads, invoices, payroll, and expenses
  - [ ] Secure authentication system (JWT)
 
  ---

  ### Invoicing
  - [ ] Customer management (CRUD)
  - [ ] Load tracking (miles, freight type, origin/destination)
  - [ ] Invoice generation logic
  - [ ] PDF invoice report
  - [ ] Email invoice to customer
 
  ---

  ### Expense Tracking
  - [ ] Add/track expenses (fuel, tolls, repairs, etc)
  - [ ] Category/tagging system
  - [ ] Expense reports (monthly, per-truck, per-driver)

  ---

  ### Payroll
  - [ ] Driver management (employee vs contractor)
  - [ ] Time/load tracking for pay calculation
  - [ ] Manual tax withholding logic for W-2 drivers
  - [ ] 1099 contractor payouts (gross only)
  - [ ] Pay stub PDF generation
  - [ ] Payroll reports (weekly/monthly)

  ---

  ### Year-End Forms
  - [ ] W-2 form generation for employees
  - [ ] 1099-NEC form generation for contractors
 
  ---

  ### Reports & Dashboard
  - [ ] Profit & loss summary
  - [ ] Outstanding invoice list
  - [ ] Payroll liability summary
  - [ ] Expenses over time

  ---

  ### Hosting and Deployment
  - [ ] Docker Compose config - App stack (backend, database, services) containerized using Docker Compose
  - [ ] Deployment to private Proxmox environment – Self-hosted on a Proxmox VE-managed machine (via VM or LXC)
  - [ ] NGINX reverse proxy + HTTPS (Let's Encrypt) – Secure traffic routing with auto-renewing SSL
  - [ ] Automated database backups – Scheduled PostgreSQL dumps and off-device archive via cron and rsync
  - [ ] Admin-only route protection + dashboard – Backend route locking, future dashboard for admin controls

  ---

  ### Extras
  - [ ] Mobile-friendly frontend (React/Tailwind)
  - [ ] Driver portal for viewing pay/invoice info
  - [ ] Fleet performance dashboard
  - [ ] Print-friendly reports

  ---

  ## 📘 Documentation

- 📦 [Deployment details](docs/deployment.md)
- 🔐 [Security model](docs/security.md) *(coming soon)*
- 🧾 [Tax logic overview](docs/payroll.md) *(coming soon)*
- 📦 [`docker-compose.yml`](./docker-compose.yml) – defines backend stack (Postgres, FastAPI, pgAdmin)
- 🐍 [`backend/main.py`](./backend/main.py) – simple FastAPI backend entrypoint
- 📘 [`docs/deployment.md`](./docs/deployment.md) – full deployment architecture and instructions
- 🔒 `.env` – local config file (not committed for security)


