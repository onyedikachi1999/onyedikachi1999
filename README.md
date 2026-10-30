# Onyedikachi Enwerem
### Python Backend & Full-Stack Engineer — Django • FastAPI • PostgreSQL • Celery/Redis • React/TypeScript

📍 **Lagos, Nigeria** *(Open to Remote & Relocation)* &nbsp;|&nbsp; 🌐 **Live Product:** [www.tmailme.com](https://www.tmailme.com) &nbsp;|&nbsp; 📫 **Email:** [enweremonyedikachi@gmail.com](mailto:enweremonyedikachi@gmail.com)

---

### ⚡ Engineering Focus

I architect and ship **high-concurrency Python backends**, **fintech payment & settlement engines**, **multi-tenant commercial ERPs**, and **full-stack React/TypeScript & Electron applications**. My work centers on:

- **Transactional Integrity & Fintech Engineering:** Two-leg atomic settlement (`transaction.atomic()`, PostgreSQL row-level locking via `select_for_update()`), idempotent webhook processing, HMAC-SHA512 signature verification, virtual account reconciliation (**Paystack, Monnify, Flutterwave**), and automated stuck-transaction recovery.
- **Defense-in-Depth API Security:** Zero-Knowledge End-to-End Encryption (**Web Crypto RSA-OAEP JWK**), **WebAuthn / Passkeys**, **TOTP 2FA**, **OAuth 2.0**, **Ed25519 cryptographic leases**, custom **6-tier RBAC**, and **16+ scoped rate-limiting middlewares**.
- **Distributed Task Pipelines & Multimodal AI:** Asynchronous **Celery + Redis** workers, **Celery Beat** data-lifecycle schedulers, and agentic **Google Gemini** function-calling & voice/SMS pipelines (**Africa's Talking, Twilio, Termii, WhatsApp Cloud API, Vosk STT, Edge TTS**).

---

### 🏗️ Flagship Production Systems & Architecture Case Studies

> *Note: Commercial SaaS/Fintech repositories (**TMailme**, **Vandara Wholesale OS**, **BUYBY**) are maintained in private repositories to protect proprietary IP. Click the **Architecture Case Study** links below to inspect their system diagrams, concurrency models, security workflows, and test suite coverage.*

| System | Architecture & Core Stack | Engineering Highlights | Live Link / Case Study / Code |
| :--- | :--- | :--- | :--- |
| **[TMailme](https://www.tmailme.com)**<br>*Privacy-First Disposable Email, Shield Aliasing & Developer API* | `Python 3.12` `Django 5.2` `DRF` `PostgreSQL` `Celery Beat` `Redis` `React 19` `TypeScript` `Chrome MV3` `Sentry` | • **Zero-Knowledge E2EE** with browser-generated RSA-OAEP public keys (JWK)<br>• **WebAuthn/Passkeys**, TOTP 2FA, Google OAuth 2.0 & JWT blacklisting<br>• **Bitwarden-compatible v1 REST Alias API** & **16 scoped DRF rate limiters**<br>• Per-minute **Celery Beat** inbox expiration & GDPR data-destruction pipelines<br>• **Manifest V3 Browser Extension** with 1-click email autofill & background OTP extraction<br>• Validated by **19 automated backend test suites** | 🟢 **[Live at tmailme.com](https://www.tmailme.com)**<br>📐 **[Architecture Case Study](./case-studies/TMAILME_ARCHITECTURE.md)** |
| **Vandara Wholesale OS**<br>*22-App Multi-Tenant Commercial ERP, POS & Voice AI Suite* | `Python 3.12` `Django` `DRF` `PostgreSQL` `Redis` `Docker` `Nginx` `React 19` `Electron` `Gemini AI` | • **22 modular Django apps** with multi-branch stock isolation & atomic stock transfers<br>• Automated credit recovery via **Monnify Virtual Accounts**, **Paystack**, **WhatsApp Cloud API / USSD** & **Termii SMS**<br>• **J.A.R.V.I.S.** multimodal voice/text copilot (**Gemini + Vosk STT + Edge TTS**) supporting Nigerian English & Pidgin<br>• **Ed25519 cryptographic lease** verification, **35+ test suites**, and packaged **Electron** Windows desktop apps | 📐 **[Architecture Case Study](./case-studies/VANDARA_ERP_ARCHITECTURE.md)** |
| **BUYBY**<br>*AI-Powered SMS & Offline-First Fintech Settlement Engine* | `Python 3.12` `Django 5.2` `PostgreSQL` `Celery` `Redis` `Monnify` `Flutterwave` `Africa's Talking` `Gemini AI` | • **2-leg atomic settlement** (`transaction.atomic()`, `select_for_update()`) for P2P, inter-bank, bulk & scheduled transfers<br>• **Monnify** card tokenization/payouts & **Flutterwave** bank account resolution<br>• Conversational **SMS banking** via Africa's Talking webhooks + **Gemini NLP intent parsing**<br>• Automated Celery failure recovery & **13 test suites** | 📐 **[Architecture Case Study](./case-studies/BUYBY_FINTECH_ARCHITECTURE.md)** |
| **GuardianLink**<br>*Multi-Tenant School Safety, Attendance & AI Risk Engine* | `Python` `Django` `DRF` `Supabase` `Celery` `Redis` `Gemini AI` `React` `TypeScript` | • **6-tier custom RBAC** (`SYSTEM_ADMIN`, `SCHOOL_ADMIN`, `SECURITY`, `TEACHER`, `PARENT`, `STUDENT`)<br>• Async **Celery + Gemini AI** student risk-scoring pipeline with exponential backoff, jitter & Redis prompt-hash caching<br>• Automated multi-channel **SMS & Email emergency alerts** + 5 role-specific React portals | 📐 **[Architecture Case Study](./case-studies/GUARDIANLINK_ARCHITECTURE.md)** |
| **Velocity Motors (`dealership-app`)**<br>*Full-Stack Automotive Marketplace & Reservation API* | `FastAPI` `SQLAlchemy 2.0` `PostgreSQL` `Celery` `Redis` `Docker` `Nginx` `GitHub Actions` `React 19` `TypeScript` | • Modular **FastAPI** backend with **SQLAlchemy 2.0**, **Pydantic v2** & JWT/bcrypt auth<br>• Custom HTTP security headers (`HSTS`, `nosniff`, `X-Frame-Options`), IP rate limiting & structured JSON logging middlewares<br>• **Celery + Termii SMS** notifications, 360° vehicle viewer, Docker Compose + Nginx & **GitHub Actions CI/CD** | 💻 **[Public Source Code](https://github.com/onyedikachi1999/dealership-app)** |
| **Kora-AI**<br>*Autonomous 6-Layer Agentic Executive Copilot* | `FastAPI` `Google GenAI SDK` `SQLAlchemy 2.0` `APScheduler` `React` `Tailwind CSS` | • 6-layer agent harness with **Gemini structured function calling** (Naira invoicing, VAT/margin math, persistent SQLAlchemy memory bank)<br>• Autonomous **APScheduler** jobs for daily WAT executive briefings & voice-note transcription | 💻 **[Public Source Code](https://github.com/onyedikachi1999/Kora-AI)** |

---

### 🛠️ Technical Toolbox

- **Languages:** Python (3.11 / 3.12), SQL, TypeScript, JavaScript (ES6+), Bash
- **Backend Frameworks:** Django (5.x / 6.x), Django REST Framework (DRF), FastAPI, SQLAlchemy 2.0, Django ORM, Alembic, Pydantic v2, Gunicorn, Uvicorn
- **Databases & Caching:** PostgreSQL, Supabase, Redis (Distributed Locks, Rate Limiting, Caching & Celery Broker), SQLite
- **Async & Messaging:** Celery, Celery Beat, APScheduler, Webhooks (HMAC-SHA512), REST APIs, OpenAPI / Swagger
- **Fintech & Telecom Integrations:** Paystack, Monnify, Flutterwave, Africa's Talking (SMS/USSD), Twilio, Termii, WhatsApp Cloud API
- **Frontend, Desktop & Extensions:** React 19, TypeScript, Vite, Tailwind CSS, TanStack Query, Zustand, Electron, Chrome Extensions (Manifest V3)
- **DevOps, Observability & Testing:** Docker (Multi-Stage Builds), Docker Compose, Nginx, GitHub Actions (CI/CD), Render, Sentry Telemetry, `pytest` / Django `TestCase`
