<img width="1924" height="1003" alt="image" src="https://github.com/user-attachments/assets/af60dbdd-92bf-4b00-ba9b-8e6af91369cb" /># 🍽️ ZeroHunger

### AI-Powered Food Redistribution & Safety Management Platform

ZeroHunger is a full-stack web application that helps reduce food waste by connecting restaurants, hotels, colleges, and event organizers with NGOs that can redistribute surplus food to communities in need.

The platform combines **Generative AI**, **real-time weather analysis**, and **intelligent NGO matching algorithms** to evaluate food safety, prioritize urgent donations, and improve the efficiency of food rescue operations.

---

## 🌍 The Problem

Millions of meals are wasted every day while many people continue to face food insecurity.

Current food donation processes are often:

* Manual and slow
* Difficult for NGOs to discover
* Lacking food safety assessment
* Inefficient in matching donors and recipients

As a result, usable food is frequently discarded before it can reach people who need it.

---

## 💡 The Solution

ZeroHunger creates a real-time bridge between food donors and NGOs.

The platform:

✅ Evaluates food safety using AI

✅ Considers environmental conditions such as temperature

✅ Calculates donation urgency levels

✅ Matches food providers with suitable NGOs

✅ Helps ensure surplus food reaches people before it becomes unsafe

---

## ✨ Key Features

### 🤖 AI Food Safety Assessment

Uses Google Gemini AI to analyze:

* Food type
* Preparation time
* Quantity
* Storage conditions

and generate:

* Risk classifications
* Remaining safe consumption windows
* Storage recommendations
* Distribution guidance

---

### 🌡️ Weather-Aware Risk Analysis

Integrates real-time weather data using Open-Meteo API.

The system:

* Retrieves local temperature information
* Calculates environmental impact on food quality
* Adjusts food safety scores dynamically
* Increases urgency for highly perishable donations

---

### 📍 Smart NGO Matching

Automatically matches food donations using:

* Geographic proximity
* NGO storage capacity
* Donation quantity
* Food safety urgency

This ensures that food reaches the most suitable NGO as quickly as possible.

---

### 🗺️ Interactive Food Map

NGOs can:

* View nearby food donations
* Locate donors on an interactive map
* Discover best-match opportunities
* Track available rescue operations

---

### 🔐 Role-Based Access Control

Separate dashboards for:

* Restaurants / Donors
* NGOs
* Administrators

powered by Firebase Authentication.

---

### 📊 Administrative Analytics

Admins can monitor:

* Active food listings
* Registered users
* Food rescue statistics
* Distribution activity
* Platform performance

---

## 🏗️ System Architecture

```text
Restaurant / Donor
        │
        ▼
Create Food Post
        │
        ▼
AI Safety Assessment
(Google Gemini)
        │
        ▼
Weather Analysis
(Open-Meteo API)
        │
        ▼
Food Safety Score
        │
        ▼
Matching Engine
(Haversine Distance + NGO Capacity)
        │
        ▼
Best NGO Match
        │
        ▼
Pickup & Distribution
```

---

## 📸 Screenshots

### Landing Page

> <img width="1924" height="1003" alt="image" src="https://github.com/user-attachments/assets/34fdfbea-d3e1-46f6-b988-121ed7fb72bc" />

### Authentication System

> <img width="630" height="575" alt="image" src="https://github.com/user-attachments/assets/dd48c8ee-335e-4858-930a-19d8dbd8f3f4" />


### NGO Dashboard

> <img width="1496" height="894" alt="image" src="https://github.com/user-attachments/assets/495afa8c-b7ef-400a-8449-d554c5fda061" />


### Admin Dashboard

> <img width="1117" height="958" alt="image" src="https://github.com/user-attachments/assets/4e3de1f4-d85d-4594-8cf9-4779e0031afa" />

---

## 🛠️ Tech Stack

### Frontend

* React 19
* TypeScript
* Vite
* Tailwind CSS
* Framer Motion
* React Leaflet

### Backend

* Node.js
* Express.js

### Database & Authentication

* Firebase Firestore
* Firebase Authentication
* Firebase Admin SDK

### AI & APIs

* Google Gemini 1.5 Flash
* Open-Meteo API
* OpenStreetMap Nominatim API

### Mapping & Geospatial

* Leaflet.js
* React Leaflet
* Haversine Distance Formula

---

## 📂 Project Structure

```text
ZeroHunger
│
├── backend
│   ├── src
│   │   ├── server.js
│   │   ├── foodExpiry.js
│   │   └── seed.js
│   └── package.json
│
└── frontend
    ├── src
    │   ├── pages
    │   ├── components
    │   ├── lib
    │   └── types
    └── package.json
```

---

## 🚀 Getting Started

### Prerequisites

* Node.js 18+
* Firebase Project
* Google Gemini API Key

---

### Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file:

```env
PORT=5000

GEMINI_API_KEY=YOUR_GEMINI_API_KEY

GOOGLE_APPLICATION_CREDENTIALS=./serviceAccount.json
```

Start backend:

```bash
npm run dev
```

---

### Frontend Setup

```bash
cd frontend
npm install
```

Create a `.env` file:

```env
VITE_FIREBASE_API_KEY=
VITE_FIREBASE_AUTH_DOMAIN=
VITE_FIREBASE_PROJECT_ID=
VITE_FIREBASE_STORAGE_BUCKET=
VITE_FIREBASE_MESSAGING_SENDER_ID=
VITE_FIREBASE_APP_ID=
```

Run frontend:

```bash
npm run dev
```

---

## 📡 API Endpoints

| Endpoint                 | Method | Description                          |
| ------------------------ | ------ | ------------------------------------ |
| `/api/match`             | POST   | Match food donations with NGOs       |
| `/api/predict-expiry`    | POST   | AI-powered food safety analysis      |
| `/api/food-safety-score` | POST   | Calculate weather-aware safety score |
| `/health`                | GET    | API health status                    |

---

## 🎯 What I Learned

Through this project, I gained practical experience with:

* Full-Stack Application Development
* Firebase Authentication & Firestore
* Large Language Model Integration
* Geospatial Calculations
* Weather API Integration
* Role-Based Access Control
* Multi-user System Design
* AI-Assisted Decision Workflows

---

## 🔮 Future Improvements

* Route optimization for pickups
* Volunteer management system
* Mobile application
* Real-time notifications
* AI image-based food quality assessment
* Advanced analytics dashboard

---

## 🧠 Development Approach

This project was rapidly prototyped using AI-assisted development tools and then customized, tested, and extended with additional functionality including AI-powered food safety assessment, weather-aware scoring, and NGO matching workflows.

---

## 👨‍💻 Author

**Mohamed Ansari**

🎓 B.E Computer Science & Engineering
📚 IIT Madras BS Degree in Programming & Data Science

GitHub: https://github.com/801PEC

---

### ⭐ If you found this project interesting, consider giving it a star.
