# Zero Hunger: AI-Integrated Food Rescue and Safety Management Platform

Zero Hunger is a sophisticated full-stack application designed to optimize the redistribution of surplus food from commercial entities to non-governmental organizations (NGOs). The platform implements advanced risk assessment through Large Language Models (LLMs), real-time environmental data integration, and automated logistical matching to ensure food safety and efficiency.

---

## Technical Overview

The platform serves three distinct user roles—Restaurants, NGOs, and Administrators—providing each with a tailored dashboard and set of management tools. The core value proposition lies in its ability to quantify food safety risks dynamically and facilitate immediate rescue operations through intelligent data processing.

### Core Algorithmic Features

#### 1. Large Language Model Risk Assessment
The system utilizes the **Google Gemini 1.5 Flash** model to perform real-time safety audits on donated food. By processing natural language inputs regarding food type, preparation time, and quantity, the model generates:
- **Risk Classification**: Categorization into Low, Medium, High, or Critical risk levels.
- **Safety Benchmarking**: Calculation of remaining safe consumption windows.
- **Actionable Intelligence**: Specific recommendations for storage and distribution handling.

#### 2. Meteorological Impact Integration
To account for environmental variables, the backend integrates with the **Open-Meteo API**.
- **Dynamic Scoring**: The system retrieves local temperature data at the point of origin.
- **Thermal Degradation Factor**: Higher ambient temperatures trigger a proportional reduction in the food's safety score, accelerating the urgency of pickup for perishable items.

#### 3. Logistical Matchmaking Algorithm
The platform automates the connection between donors and recipients using a multi-factor scoring algorithm:
- **Geospatial Proximity**: Calculation of distances using the **Haversine Formula**.
- **Capacity Analysis**: Matching food volume against NGO storage and distribution capabilities.
- **Urgency Weighting**: Prioritizing "Critical" risk posts for immediate NGO notification and matching.
- **Geocoding Fallback**: Implementation of OpenStreetMap (Nominatim) for address-to-coordinate conversion when GPS data is unavailable.

---

## Technology Stack

### Frontend Architecture
- **Core Framework**: React 19 (TypeScript)
- **Tooling**: Vite for optimized builds and development.
- **Interface Design**: Tailwind CSS for responsive layout and Framer Motion for interface transitions.
- **GIS Integration**: Leaflet.js and React-Leaflet for geospatial visualization.
- **Authentication**: Role-Based Access Control (RBAC) via Firebase Authentication.

### Backend Infrastructure
- **Runtime Environment**: Node.js with Express.js.
- **Database Architecture**: Google Firebase Firestore (NoSQL) for real-time document synchronization.
- **Administrative Logic**: Firebase Admin SDK for secure server-side operations and user management.
- **External API Integration**: Fetch API for Gemini LLM, Open-Meteo, and Nominatim services.

---

## Project Structure

```text
├── backend
│   ├── src
│   │   ├── server.js          # Primary API entry point and algorithmic logic
│   │   ├── foodExpiry.js      # Heuristic database for localized food items
│   │   └── seed.js            # Database initialization and mock data generation
│   ├── package.json           # Node.js dependencies and scripts
│   └── serviceAccount.json    # Firebase administrative credentials
└── frontend
    ├── src
    │   ├── pages              # Role-specific dashboard implementations
    │   ├── components         # Atomic UI components and layout providers
    │   ├── lib                # Core library configurations (Firebase, RBAC)
    │   └── types              # TypeScript interface definitions
    ├── tailwind.config.js     # Design system configuration
    └── package.json           # Frontend dependencies and Vite configuration
```

---

## Installation and Execution

### Prerequisites
- Node.js version 18.0.0 or higher.
- A configured Firebase project with Firestore and Authentication enabled.
- A valid Google Gemini API Key.

### Initial Setup
1. **Extract Project Files**: Decompress the `Main app.zip` archive into your desired workspace.
2. **Directory Navigation**: Open a terminal and navigate to the root of the extracted directory.

### Backend Configuration
1. **Navigate to Directory**: `cd backend`
2. **Install Dependencies**: `npm install`
3. **Environment Setup**: Create a `.env` file with the following parameters:
   ```env
   PORT=5000
   GEMINI_API_KEY=your_gemini_api_key
   # Path to your Firebase service account JSON file
   GOOGLE_APPLICATION_CREDENTIALS=./serviceAccount.json
   ```
4. **Initialize Server**: `npm run dev`

### Frontend Configuration
1. **Navigate to Directory**: `cd ../frontend`
2. **Install Dependencies**: `npm install`
3. **Environment Setup**: Create a `.env` file containing your Firebase client-side credentials:
   ```env
   VITE_FIREBASE_API_KEY=your_key
   VITE_FIREBASE_AUTH_DOMAIN=your_domain
   VITE_FIREBASE_PROJECT_ID=your_id
   VITE_FIREBASE_STORAGE_BUCKET=your_bucket
   VITE_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
   VITE_FIREBASE_APP_ID=your_app_id
   ```
4. **Execute Application**: `npm run dev`

---

## API Documentation (Selected Endpoints)

| Endpoint | Method | Description |
| :--- | :--- | :--- |
| `/api/match` | POST | Executes the NGO matching algorithm for a specific food post. |
| `/api/predict-expiry` | POST | Interfaces with Gemini AI to determine food safety windows. |
| `/api/food-safety-score` | POST | Calculates an aggregate safety score incorporating weather data. |
| `/health` | GET | Returns the operational status of the backend API. |

---

## Interface Snapshots

Standardized view of the platform interfaces across different user roles.

| Administrative Interface | Restaurant Management | NGO Operational View |
| :--- | :--- | :--- |
| [Placeholder for Admin Dashboard] | [Placeholder for Restaurant Dashboard] | [Placeholder for NGO Activity] |

---

## License

This project is distributed under the ISC License.
