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

[✨ Features](#-features) · [📐 Architecture](#-system-architecture) · [🛠 Tech Stack](#-tech-stack) · [🚀 Quick Start](#-quick-start) · [📡 API Reference](#-api-reference) · [⚙️ Configuration](#-configuration-reference)

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
Here is the new README.md for your GAL — Gamified AI Learning Platform project, beautifully formatted using the structure, aesthetic, and professional standard of the SkillStack AI repository.Markdown# 🚀 GAL — Gamified AI Learning Platform

<div align="center">

![GAL Banner](https://img.shields.io/badge/GAL-Gamified%20AI%20Learning-6366f1?style=for-the-badge&logo=google-gemini&logoColor=white)

[![Python](https://img.shields.io/badge/Python-3.12-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![Flask](https://img.shields.io/badge/Flask-3.x-000000?style=flat-square&logo=flask&logoColor=white)](https://flask.palletsprojects.com)
[![JavaScript](https://img.shields.io/badge/Vanilla-JS-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Gemini AI](https://img.shields.io/badge/Google-Gemini%202.0%20Flash-4285F4?style=flat-square&logo=google&logoColor=white)](https://ai.google.dev)
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas%20%2F%20JSON-47A248?style=flat-square&logo=mongodb&logoColor=white)](https://mongodb.com)
[![Firebase](https://img.shields.io/badge/Firebase-Realtime%20DB-FFCA28?style=flat-square&logo=firebase&logoColor=black)](https://firebase.google.com)

**An immersive, game-based learning system for AI, programming, and computer science. Built with a lightweight architecture (Flask + Vanilla JS) requiring absolutely no build step, featuring live telemetry, custom charting, and an integrated AI tutor.**

[✨ Features](#-features) · [📐 Architecture](#-system-architecture) · [🛠 Tech Stack](#-tech-stack) · [🚀 Quick Start](#-quick-start) · [📡 API Reference](#-api-reference) · [⚙️ Configuration](#-configuration-reference)

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

###System Interaction Diagram
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
