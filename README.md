# 🚀 GAL — Gamified AI Learning Platform

<div align="center">

![GAL Banner](https://img.shields.io/badge/GAL-Gamified%20AI%20Learning-6366f1?style=for-the-badge&logo=google-gemini&logoColor=white)

[![Python](https://img.shields.io/badge/Python-3.12-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![Flask](https://img.shields.io/badge/Flask-3.x-000000?style=flat-square&logo=flask&logoColor=white)](https://flask.palletsprojects.com)
[![JavaScript](https://img.shields.io/badge/Vanilla-JS-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Gemini AI](https://img.shields.io/badge/Google-Gemini%202.0%20Flash-4285F4?style=flat-square&logo=google&logoColor=white)](https://ai.google.dev)
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas%20%2F%20JSON-47A248?style=flat-square&logo=mongodb&logoColor=white)](https://mongodb.com)
[![Firebase](https://img.shields.io/badge/Firebase-Realtime%20DB-FFCA28?style=flat-square&logo=firebase&logoColor=black)](https://firebase.google.com)

**An immersive, game-based learning system for AI, programming, and computer science. Built with a lightweight architecture (Flask + Vanilla JS) requiring absolutely no build step, featuring live telemetry, custom charting, and an integrated AI tutor.**

[✨ Features](#-features) · [📐 Architecture](#-system-architecture) · [🛠 Tech Stack](#-tech-stack) · [🚀 Quick Start](#-quick-start) · [📡 API Reference](#-api-reference) · [⚙️ Configuration](#️-configuration-reference)

</div>

---

## 🎯 Problem Statement

Traditional computer science and artificial intelligence learning platforms often suffer from high drop-off rates due to static text-heavy curriculums and a lack of interactive engagement. Students struggle to visualize their progress and often lack on-demand assistance when they hit roadblocks.

**GAL solves this** by transforming the educational journey into an immersive, gamified experience. By combining playable game modules (like Haunted Mansion and Shadow Query) with real-time telemetry, competitive team leaderboards, and an always-available Gemini AI tutor, GAL bridges the gap between entertainment and technical education.

---

## 🌟 Proposed Solution

GAL is a unified **Flask 3.x + Vanilla JS** web platform built for high interactivity without the overhead of heavy frontend frameworks. The system features:

1. **Interactive Game Modules:** Dedicated HTML5 game pages (Haunted Mansion, Code Red, Shadow Query, Treasure Hunt) that teach concepts through gameplay.
2. **Real-Time Telemetry:** A custom `gal-telemetry.js` module that asynchronously tracks player sessions, accuracy, and scores.
3. **Dynamic Visualizations:** A custom Canvas-based chart library (`gal-charts.js`) rendering radar, line, bar, and ring charts to visualize player skills and XP.
4. **AI Tutoring:** A direct proxy to Google's Gemini 2.0 Flash model, allowing students to ask contextual questions during their learning journey.
5. **Dual-Mode Database:** Seamlessly scales from a local JSON database for rapid development to MongoDB Atlas for production.

---

## ✨ Features

### 🎮 1. Immersive Game-Based Modules
Different modules targeting various facets of programming and problem-solving:

| Game Module | Description | Technology |
|---|---|---|
| **Haunted Mansion** | Logic and algorithm puzzle environment | Vanilla JS / Canvas |
| **Code Red** | High-stakes programming and debugging | Vanilla JS |
| **Shadow Query** | Database and SQL injection learning | Vanilla JS |
| **Treasure Hunt** | Data structures and traversal challenges | Vanilla JS |

### 📊 2. Live Telemetry & Custom Analytics
A lightweight, fire-and-forget telemetry system tracking learning metrics:

| Feature | Implementation | Use Case |
|---|---|---|
| Session Tracking | `Telemetry.startSession()` & `endSession()` | Measure time spent on specific concepts |
| Event Logging | `Telemetry.logEvent()` | Track specific interactions (e.g., correct answers) |
| Canvas Charts | `GALCharts.radar()`, `GALCharts.line()` | Visualise skill distribution (Python vs ML vs SQL) and XP growth over time |

### 🤖 3. AI Tutor Integration
- **Gemini Proxy:** Securely routes AI chat requests through the Flask backend (`/api/ai_chat`) to hide API keys from the client.
- **Contextual Help:** Students can access the `gemini-chat.html` page to get explanations for difficult computer science concepts.

### 🏆 4. Teams & Leaderboards
- **Global Leaderboards:** Top 20 players ranked globally.
- **Team Dynamics:** Create teams, join via code, and compete on the Top 10 Team Leaderboard.

---

## 📐 System Architecture

### Directory Structure

```text
Gamified-Ai-learning-website-LEVELUP-AI/
│
├── app.py                      # Flask entry point (routes + startup)
├── gal_config.js               # Shared frontend config (API key, base URL)
├── requirements.txt            # Python dependencies
├── .env                        # Environment variables (gitignored)
│
├── core/                       # Backend core modules
│   ├── config.py               # Env vars, MongoDB, Firebase setup
│   ├── db.py                   # DB helpers (JSON + MongoDB dual-mode)
│   └── firebase.py             # Firebase Realtime Database helpers
│
├── api/                        # Flask Blueprints (one file per route group)
│   ├── auth.py                 # Account creation and session management
│   ├── profile.py              # Profile and stat updates
│   ├── progress.py             # Level completion tracking
│   ├── leaderboard.py          # Global ranking engine
│   ├── study.py                # Study module management
│   ├── team.py                 # Team creation and leaderboards
│   └── ai_chat.py              # Google Gemini proxy route
│
├── static/
│   └── js/
│       ├── gal-telemetry.js    # Async fire-and-forget event tracking
│       └── gal-charts.js       # Canvas chart library (Radar, Line, Bar, Ring)
│
├── data/
│   └── db.json                 # Local JSON database (auto-created for dev)
│
└── pages/                      # HTML game pages (served directly by Flask)
    ├── index.html              # Landing / auth page
    ├── dashboard.html          # Player dashboard
    ├── hauntedmansion.html     # Game Module
    ├── codered.html            # Game Module
    ├── shadowquery.html        # Game Module
    ├── treasurehunt.html       # Game Module
    └── gemini-chat.html        # AI Chat interface
```

### System Interaction Diagram

```text
┌──────────────────────────────────────────────────────────────────────────┐
│                             GAL Platform                                 │
│                                                                          │
│  ┌─────────────┐      ┌──────────────────────────────────────────────┐   │
│  │   Browser   │      │              Flask Backend                   │   │
│  │             │      │                                              │   │
│  │ gal-charts  │◄────►│  ┌─────────────┐    ┌──────────────────┐    │   │
│  │ gal-telemet │      │  │ API Routing │    │   AI Integration │    │   │
│  │             │      │  │ (Blueprints)│    │   Gemini 2.0     │    │   │
│  │ Game Canvas │◄────►│  └──────┬──────┘    │   Flash          │    │   │
│  │             │      │         │           └─────────┬────────┘    │   │
│  │ AI Chat UI  │◄────►│  ┌──────▼─────────────────────▼────────┐    │   │
│  └─────────────┘      │  │           Core Logic                │    │   │
│                        │  └──────┬─────────────────────┬────────┘    │   │
│                        │         │                     │             │   │
│                        │  ┌──────▼──────┐       ┌──────▼──────┐      │   │
│                        │  │  MongoDB /  │       │  Firebase   │      │   │
│                        │  │  Local JSON │       │ Realtime DB │      │   │
│                        │  └─────────────┘       └─────────────┘      │   │
│                        └──────────────────────────────────────────────┘   │
│                                                                          │
└──────────────────────────────────────────────────────────────────────────┘
```

---

## 🛠 Tech Stack

| Layer | Technology | Purpose |
|---|---|---|
| **Backend** | Python 3.12 + Flask 3.x | Core API routing and server-side logic |
| **Database (Dev)** | Local JSON File (`db.json`) | Zero-config local development |
| **Database (Prod)**| MongoDB Atlas (PyMongo) | Scalable production data storage |
| **Realtime** | Firebase Realtime DB | Live state synchronization (Optional) |
| **AI** | Google Gemini 2.0 Flash | AI Tutoring via `/api/ai_chat` |
| **Frontend** | Vanilla HTML/CSS/JS | Lightning-fast rendering, zero build steps |
| **Data Viz** | Custom Canvas API | Native rendering for Radar, Line, Bar, and Ring charts |

---

## 🚀 Quick Start

### Prerequisites
- Python 3.12+
- Google Gemini API Key

### 1. Clone the Repository
```bash
git clone [https://github.com/your-username/gal-platform.git](https://github.com/your-username/gal-platform.git)
cd gal-platform
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
# Installs flask, python-dotenv, pymongo
```

### 3. Configure Environment Variables
Create a `.env` file in the project root (see [Configuration](#-configuration-reference)).

### 4. Run the Server
```bash
python app.py
```

### 5. Start Learning
Open your browser and navigate to `http://localhost:5050`

---

## 📡 API Reference

### Authentication (`/api/auth.py`)
| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/register` | Create a new player account |
| `POST` | `/api/login` | Authenticate player and create session |
| `POST` | `/api/logout` | Terminate current session |

### Player & Progress (`/api/profile.py`, `/api/progress.py`)
| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/profile` | Retrieve full player profile and XP |
| `POST` | `/api/update_stats` | Submit game score / XP payload |
| `GET` | `/api/progress` | Get per-game level completion status |
| `POST` | `/api/progress/complete_level`| Mark a specific level as completed |
| `GET` | `/api/leaderboard` | Retrieve the global Top 20 players |

### Study Modules (`/api/study.py`)
| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/study/modules` | List all study modules and completion status |
| `POST` | `/api/study/complete` | Mark a specific module as complete |

### Teams (`/api/team.py`)
| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/team/create` | Create a new study/competitive team |
| `POST` | `/api/team/join` | Join a team using a unique code |
| `GET` | `/api/team/info` | Fetch details of the current user's team |
| `GET` | `/api/team/leaderboard` | Retrieve the Top 10 teams |

### AI & Misc (`/api/ai_chat.py`, `app.py`)
| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/ai_chat` | Communicate with the Gemini AI Tutor |
| `GET` | `/api/health` | Server health check and feature flag status |

---

## ⚙️ Configuration Reference

Create a `.env` file in the root directory. The system automatically falls back to a local JSON database if MongoDB/Firebase keys are not provided.

| Variable | Required | Description |
|---|---|---|
| `GEMINI_API_KEY` | ✅ Yes | Google Gemini API key for the AI Tutor module |
| `MONGODB_URI` | No | MongoDB Atlas connection string (Falls back to `data/db.json` if empty) |
| `MONGODB_DB` | No | Database name (Default: `gal`) |
| `FIREBASE_CRED_PATH`| No | Path to Firebase service account JSON file |
| `FIREBASE_DB_URL` | No | Firebase Realtime Database URL |

---

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/new-game-module`
3. Commit your changes: `git commit -m 'feat: added new regex mini-game'`
4. Push to the branch: `git push origin feature/new-game-module`
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License**.

---

<div align="center">

**Level up your learning. Built to make education an adventure.**

</div>
