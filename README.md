# 🗓️ CSI Meeting Manager
### Utilitaire de Gestion des Réunions & Recommandations — ART

> **Agence de Régulation des Télécommunications (ART)**  
> Cellule des Systèmes d'Information (CSI)

---

## 📌 About The Project

The **CSI Meeting Manager** is a web application built to solve a real operational problem faced by the CSI team at ART. The team holds regular coordination and work meetings, but struggled with three major issues:

- 📂 Meeting minutes were **scattered and hard to find**
- ✅ Decisions (résolutions) were **forgotten or not followed up**
- 💡 Recommendations were **not tracked or implemented**

This utility centralises all meeting management, decision tracking, and recommendation follow-up in one professional web interface.

---

## ✨ Key Features

| Module | Description |
|--------|-------------|
| 🗓️ **Meetings** | Create, edit, archive meetings with full metadata (date, time, location, type, participants, minutes) |
| ✅ **Résolutions** | Record decisions from each meeting, assign responsible persons, set deadlines, track status |
| 📜 **Status History** | Full audit trail — every status change is logged with who changed it and when |
| 💡 **Recommendations** | Link recommendations to decisions, set priority levels, track execution rate (0–100%) |
| 🔔 **Notifications** | Automatic alerts for upcoming deadlines and overdue tasks |
| 📊 **Dashboard** | Real-time statistics — total meetings, resolved decisions, overdue items, critical recommendations |
| 🔍 **Search & Filter** | Multi-criteria search by date, status, responsible person, service |
| 📤 **Export** | Export data to PDF and Excel |

---

## 🛠️ Tech Stack

```
Backend  → Django 4.x (Python)
API      → Django REST Framework (DRF)
Frontend → HTML5 + Bootstrap 5 + CSS3
Database → SQLite (development) / PostgreSQL (production)
Auth     → Django built-in authentication + Token Auth
Storage  → Local filesystem / Django media
```

---

## 🗂️ Project Structure

```
csi-meeting-manager/
│
├── csi_project/          # Django project settings & main URLs
├── meetings/             # Meeting management module
├── resolutions/          # Résolutions & status history module
├── recommendations/      # Recommendations module
├── accounts/             # User authentication & profiles
├── templates/            # HTML templates (Bootstrap 5)
│   ├── base.html
│   ├── dashboard.html
│   ├── meetings/
│   ├── resolutions/
│   └── recommendations/
├── docs/                 # ER Diagram & technical documentation
│   └── csi_er_diagram.drawio
├── requirements.txt
├── manage.py
└── README.md
```

---

## 🗄️ Database Schema (ER Diagram)

The database contains **6 tables** and **8 relationships**:

```
Users ──────────────────► Meetings (1 organizer → N meetings)
Users ──────────────────► Participants (1 user → N participations)
Meetings ───────────────► Participants (1 meeting → N participants)
Meetings ───────────────► Resolutions (1 meeting → N decisions)
Users ──────────────────► Resolutions (1 user is responsible for N resolutions)
Resolutions ────────────► StatusHistory (1 resolution → N status changes)
Users ──────────────────► StatusHistory (1 user changes N statuses)
Resolutions ────────────► Recommendations (1 resolution → N recommendations)
```

> See `docs/csi_er_diagram.drawio` for the full visual diagram (open with [draw.io](https://app.diagrams.net))

---

## ⚙️ Installation & Setup

### Prerequisites
- Python 3.10+
- pip
- Git

### Steps

```bash
# 1. Clone the repository
git clone https://github.com/YourUsername/csi-meeting-manager.git
cd csi-meeting-manager

# 2. Install dependencies
pip install -r requirements.txt

# 3. Apply database migrations
python manage.py migrate

# 4. Create an admin account
python manage.py createsuperuser

# 5. Run the development server
python manage.py runserver
```

Then open your browser at: **http://127.0.0.1:8000**

Admin panel: **http://127.0.0.1:8000/admin**

---

## 🌿 Git Branch Strategy

| Branch | Purpose |
|--------|---------|
| `main` | Stable production-ready code |
| `feature/django-setup` | Initial Django project + app structure |
| `feature/database-models` | All models, admin, forms, views, URLs |
| `feature/frontend-dashboard` | HTML templates, Bootstrap UI, dashboard |
| `docs/er-diagram-documentation` | ER diagram + README + technical docs |

---

## 📋 Project Phases (12 Weeks)

| Phase | Weeks | Description |
|-------|-------|-------------|
| 📐 Planification & Conception | 1–2 | ER diagram, wireframes, GitHub setup |
| ⚙️ Configuration Backend | 3–5 | Django, database, API REST, authentication |
| 🎨 Développement Frontend | 6–8 | HTML pages, Bootstrap UI, API integration |
| 🔧 Fonctionnalités Complètes | 9–10 | CRUD, filtering, notifications, dashboard |
| 🧪 Tests & Correction de Bugs | 11 | Unit tests, integration tests, QA report |
| 🚀 Déploiement & Documentation | 12 | Production deployment, user manual, final report |

---

## 👥 Team

| Role | Responsibilities |
|------|-----------------|
| **Superviseur** | Orientation, approbation et revue finale |
| **Chef de Projet (PM)** | Planification, suivi, assignation des tâches, coordination |
| **Développeur 1** | Backend, API, modèles de base de données, fonctionnalités principales |
| **Développeur 2** | Frontend, tests, corrections de bugs, dashboard, documentation |

---

## 📄 License

This project and all its deliverables are the intellectual property of **Agence de Régulation des Télécommunications (ART)**.  
All rights reserved — internal use only.

---

## 📞 Contact

**CSI — Cellule des Systèmes d'Information**  
Direction Générale — ART  
Yaoundé, Cameroun

---

*Built with ❤️ by the CSI Development Team*
