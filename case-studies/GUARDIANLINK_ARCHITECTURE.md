# GuardianLink — Multi-Tenant School Safety & AI Behavioral Risk Platform
**Repository Visibility:** 🔒 Private Repository *(Architecture & System Design Case Study)*

---

## 1. Executive Summary
**GuardianLink** is a multi-tenant school safety, gate entry/exit tracking, classroom attendance, and AI behavioral risk-scoring platform built in **Python, Django, Django REST Framework (DRF), PostgreSQL (Supabase), Celery, Redis, Google Gemini AI, and React + TypeScript**.

---

## 2. System Architecture & 6-Tier RBAC Pipeline

```mermaid
flowchart TB
    subgraph Portals["5 Role-Specific React + TypeScript Portals"]
        P1["System Admin Portal"]
        P2["School Admin Portal"]
        P3["Security Gate Portal"]
        P4["Teacher Attendance Portal"]
        P5["Parent Notification Portal"]
    end

    subgraph Backend["Django + DRF Core API (/api/v1/)"]
        RBAC["6-Tier Custom RBAC & Permission Guards<br/>(SYSTEM_ADMIN • SCHOOL_ADMIN • SECURITY • TEACHER • PARENT • STUDENT)"]
        ATT["Bulk Attendance & Gate Entry/Exit Engine"]
        AIC["Admin AI Chatbot & Incident Report Engine"]
    end

    subgraph AsyncAI["Asynchronous AI Risk Pipeline (Celery + Redis)"]
        TASK["update_student_risk_task<br/>(Exponential Backoff + Jitter)"]
        CACHE["Redis Prompt-Hash Cache<br/>(ai_cache.py)"]
        GEM["Google Gemini Risk & Summary Engine"]
        NOTIFY["send_high_risk_notification<br/>(Multi-Channel SMS & Email Dispatch)"]
    end

    subgraph Storage["Data & Audit Persistence"]
        DB[("PostgreSQL (Supabase)<br/>StudentRiskScore • StudentRiskHistory • AIAuditLog")]
    end

    Portals --> RBAC
    RBAC --> ATT & AIC
    ATT --> DB
    ATT --> TASK
    TASK --> CACHE --> GEM
    GEM --> DB
    TASK --> NOTIFY
```

---

## 3. Core Backend Engineering Highlights

### A. 6-Tier Role-Based Access Control (`backend/core/models.py`, `permissions.py`)
- Custom `User` model (`USERNAME_FIELD = 'email'`) with strict role isolation (`SYSTEM_ADMIN`, `SCHOOL_ADMIN`, `SECURITY`, `TEACHER`, `OTHER_STAFF`, `STUDENT`, `PARENT`) and custom queryset managers (`StudentQuerySet`) ensuring school admins and teachers can only query records belonging to their registered institution.

### B. Asynchronous AI Behavioral Risk Engine (`backend/core/tasks.py`, `backend/ai/services/`)
- `update_student_risk_task` runs asynchronously via **Celery** with automatic retry (`autoretry_for=(Exception,), retry_backoff=30, max_retries=3, retry_jitter=True`).
- Evaluates attendance anomalies and incident reports using **Google Gemini**, stores longitudinal risk trajectories in `StudentRiskHistory`, and logs input/output prompt hashes in `AIAuditLog` for governance and auditability.
- When a student's risk level crosses into `HIGH`, `notify_high_risk_student` dispatches immediate **SMS** (via Africa's Talking / Twilio) and **Email** alerts to school administrators and assigned teachers.
