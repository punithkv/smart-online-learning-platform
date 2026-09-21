<div align="center">

# 🎓 Smart Online Learning Platform
### *A Django REST + React course platform — currently in early scaffolding*

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![Django](https://img.shields.io/badge/Django-REST%20Framework-092E20?logo=django&logoColor=white)
![React](https://img.shields.io/badge/React-Planned-61DAFB?logo=react&logoColor=black)
![Status](https://img.shields.io/badge/status-early%20scaffolding-yellow)
![License](https://img.shields.io/badge/license-MIT-green)

</div>

---

## 📖 Table of Contents
- [Overview](#-overview)
- [Project Status](#-project-status)
- [Architecture (Planned)](#-architecture-planned)
- [Tech Stack](#-tech-stack)
- [Folder Structure](#-folder-structure)
- [Setup](#-setup)
- [API Reference](#-api-reference)
- [Roadmap](#-roadmap)

---

## 🔭 Overview

**Smart Online Learning Platform** is planned as a full-stack course platform: a Django REST Framework backend serving course/lesson data and handling authentication, paired with a React frontend for browsing and taking courses.

**Right now, only a small backend slice is functional** — a `Course` and `Lesson` data model with a single read-only API endpoint to list courses. Everything else (authentication, the frontend, lesson delivery, enrollment) is scaffolded as empty files or not yet started.

---

## 🚦 Project Status

> ⚠️ This project is **not runnable as-is**. `backend/backend/settings.py` — the core Django configuration file — is currently **empty**, so the server won't start until it's filled in. Treat this README as a map of what exists vs. what's planned, not a description of a working app.

| Component | Status |
|---|---|
| `courses` app (models, serializer, GET endpoint) | ✅ Implemented |
| `users` app (models, views, serializers, urls) | ❌ Empty stub files only |
| Django `settings.py` | ❌ Empty — app cannot run yet |
| JWT authentication | ❌ Not implemented (SimpleJWT not yet wired in) |
| React frontend | ❌ `frontend/` folder exists but is empty |
| `requirements.txt` | ❌ Missing |
| Database migrations | ❌ Not yet generated |

---

## 🏗 Architecture (Planned)

```
┌─────────────────────┐        REST API        ┌──────────────────────────┐
│   React Frontend        │  ◀───────────────────▶  │   Django REST Backend         │
│  (not yet built)          │                         │                                │
└─────────────────────────┘                         └──────────────┬─────────────────┘
                                                                    │
                                        ┌───────────────────────────┼───────────────────────────┐
                                        ▼                           ▼                           ▼
                              ┌──────────────────┐       ┌──────────────────┐       ┌──────────────────┐
                              │   users app          │       │   courses app        │       │   SQLite DB           │
                              │  (JWT auth —            │       │  (Course, Lesson —      │       │  (not yet migrated)     │
                              │   not implemented)         │       │   list endpoint live)      │       │                            │
                              └──────────────────┘       └──────────────────┘       └──────────────────┘
```

---

## 🧰 Tech Stack

| Layer | Technology | Status |
|---|---|---|
| **Backend framework** | Django + Django REST Framework | Partially set up |
| **Authentication** | JWT via SimpleJWT | Planned, not implemented |
| **Frontend** | React.js + Axios | Planned, no code yet |
| **Database** | SQLite (dev) | Models defined, not migrated |

---

## 🗂 Folder Structure

```
smart-online-learning-platform-main/
├── backend/
│   ├── manage.py
│   ├── backend/
│   │   ├── settings.py       # ⚠️ Empty — needs full Django config
│   │   ├── urls.py             # Wires in courses.urls under /api/
│   │   ├── wsgi.py / asgi.py
│   ├── users/
│   │   ├── models.py             # Empty — just imports User
│   │   ├── views.py                # Empty
│   │   ├── serializers.py            # Empty
│   │   └── urls.py                     # Empty
│   └── courses/
│       ├── models.py                     # Course, Lesson models
│       ├── views.py                        # get_courses (GET /api/courses/)
│       ├── serializers.py                    # CourseSerializer
│       └── urls.py                             # /courses/ route
├── frontend/                                     # Empty — no React app scaffolded yet
└── README.md
```

---

## 🚀 Setup

The backend needs configuration before it can run. To get it working locally:

### 1. Populate `settings.py`
`backend/backend/settings.py` is currently empty. Generate a fresh Django settings file (e.g. via `django-admin startproject` in a scratch folder and copying the relevant sections), then add:
- `'rest_framework'`, `'courses'`, and `'users'` to `INSTALLED_APPS`
- A `DATABASES` config (SQLite is simplest to start)
- `ROOT_URLCONF = 'backend.urls'`

### 2. Create a `requirements.txt`
None exists yet. At minimum:
```
Django
djangorestframework
djangorestframework-simplejwt
```

### 3. Install, migrate, and run
```bash
cd backend
pip install -r requirements.txt
python manage.py makemigrations
python manage.py migrate
python manage.py runserver
```

### 4. Frontend
`frontend/` has no files yet — it needs to be scaffolded first, e.g.:
```bash
cd frontend
npx create-react-app .
npm install axios
npm start
```

---

## 📡 API Reference

| Method | Endpoint | Status |
|---|---|---|
| `GET` | `/api/courses/` | ✅ Working — returns all courses |
| — | Lesson endpoints | ❌ Not implemented (model exists, no view/serializer yet) |
| — | Auth endpoints (`/api/users/...`) | ❌ Not implemented |

---

## 🛣 Roadmap

- [ ] Fill in `backend/backend/settings.py` so the server can actually run
- [ ] Add `requirements.txt`
- [ ] Implement `users` app: registration, login, JWT issuing via SimpleJWT
- [ ] Add lesson endpoints (list/detail) in `courses`
- [ ] Generate and commit initial migrations
- [ ] Scaffold the React frontend and connect it to the API via Axios
- [ ] Add course enrollment and progress tracking
- [ ] Add an instructor/admin dashboard

---

<div align="center">

Early-stage project — this README tracks real progress rather than aspirational features.

</div>