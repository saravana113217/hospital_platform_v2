# 🏥 MedCore AI — Patient Experience Platform

Enterprise-grade hospital management system built with Flask + SQLite.

## 📂 Project Structure

```
hospital_platform/
├── app.py                  ← Flask backend (all API routes)
├── hospital.db             ← SQLite database (auto-created)
├── requirements.txt
├── templates/
│   └── index.html          ← Single-page app shell
└── static/
    ├── style.css           ← Dark hospital dashboard theme
    └── script.js           ← All frontend logic
```

## 🗄️ Database Schema

**patients** — Patient registry
- `id` TEXT PRIMARY KEY (e.g. PX-12345)
- `name`, `age`, `gender`, `phone`, `department`
- `created_at` TIMESTAMP

**complaints** — Patient complaints
- `id` TEXT PRIMARY KEY (e.g. CMP-12345)
- `patient_id`, `patient_name`, `department`
- `severity` (Low/Medium/High/Critical)
- `description`, `status` (Open/In Progress/Resolved)
- `created_at`, `updated_at`

**notifications** — System alerts
- `id`, `message`, `type`, `read`, `created_at`

**settings** — Key-value config store
- `key`, `value`

## ⚡ Quick Start

### 1. Install Python 3.8+
Ensure Python 3.8 or higher is installed.

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the Application
```bash
python app.py
```

### 4. Open in Browser
```
http://localhost:5000
```

The database is auto-created and seeded with demo data on first run.

## 🎯 Features

| Feature | Description |
|---------|-------------|
| Dashboard | Real-time metrics, charts, activity feed |
| Patients | Register, search, filter, view detail |
| Complaints | Submit, manage, filter, update status |
| Analytics | Department pie, severity bar, trend line |
| Notifications | Critical alerts, mark all read |
| AI Chatbot | Simulated hospital assistant |
| Admin Panel | System status, data management |
| Settings | Toggle alerts, AI monitoring |

## 🔑 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | /api/dashboard | Dashboard stats |
| GET/POST | /api/patients | List / Register patient |
| GET | /api/patients/:id | Patient detail + complaints |
| GET/POST | /api/complaints | List / Submit complaint |
| PATCH | /api/complaints/:id | Update status |
| GET | /api/analytics | Analytics data |
| GET | /api/notifications | All notifications |
| POST | /api/notifications/read | Mark all read |
| GET/POST | /api/settings | Get / Save settings |
| POST | /api/admin/clear | Clear data |
| GET | /api/admin/status | System status |
| POST | /api/chat | AI chatbot response |
