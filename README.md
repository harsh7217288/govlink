# GovConnect – AI-Powered Civic Issue Reporting Platform

GovConnect is a prototype civic-tech platform that allows citizens to report local infrastructure problems (potholes, broken street lights, water leaks, etc.).
The system uses **AI-powered NLP classification (HuggingFace Transformers)** to automatically categorize issues and display real-time analytics through a transparency dashboard.

The project consists of a **React frontend**, **FastAPI backend**, and **PostgreSQL database**.

---

## Features

* Submit civic issues with location tagging
* AI-based automatic classification of complaints
* Real-time community issue dashboard
* Transparency analytics page with charts
* Interactive city map with issue markers
* PostgreSQL data persistence
* FastAPI backend API
* React + Tailwind frontend UI

---

## AI Component

The system uses a **HuggingFace Zero-Shot Classification model** (`facebook/bart-large-mnli`) to determine the category of a complaint.

Example:

| Complaint                 | AI Category |
| ------------------------- | ----------- |
| Pothole on Main Road      | Roads       |
| Street light broken       | Electricity |
| Water leakage near market | Water       |

The predicted category is automatically stored in the database and used by the transparency dashboard.

---

##  Tech Stack

### Frontend

* React
* TypeScript
* TailwindCSS
* Recharts (data visualization)
* Leaflet (maps)

### Backend

* FastAPI
* SQLAlchemy
* Pydantic
* HuggingFace Transformers

### Database

* PostgreSQL
  
#  Installation Guide

## 1️⃣ Clone the Repository

# Backend Setup (FastAPI)

## 2️⃣ Create Virtual Environment

```
python -m venv venv
```

Activate environment

Windows:

```
venv\Scripts\activate
```

Mac/Linux:

```
source venv/bin/activate
```

---

## 3️⃣ Install Backend Dependencies

```
pip install fastapi uvicorn sqlalchemy psycopg2-binary pydantic transformers torch
```

---

## 4️⃣ Configure PostgreSQL Database

Update `database.py`:

```
DATABASE_URL = "postgresql://username:password@localhost:5432/govconnect"
```

Create database in PostgreSQL:

```
CREATE DATABASE govconnect;
```

---

## 5️⃣ Run Backend Server

```
uvicorn main:app --reload
```

API will run at:

```
http://127.0.0.1:8000
```

Swagger Docs:

```
http://127.0.0.1:8000/docs
```

---

# Frontend Setup (React)

## 6️⃣ Install Dependencies

Navigate to frontend folder:

```
cd frontend
```

Install packages:

```
npm install
```

---

## 7️⃣ Start Frontend

```
npm run dev
```

App will run at:

```
http://localhost:5173
```

---

# 🔗 API Endpoints

| Method | Endpoint        | Description             |
| ------ | --------------- | ----------------------- |
| GET    | `/api/issues`   | Get all reported issues |
| POST   | `/api/issues`   | Submit new issue        |
| GET    | `/api/timeline` | Dashboard timeline data |

---

# 📊 Transparency Dashboard

The transparency page visualizes civic performance using:

* Reports by category
* Resolution status
* Monthly performance trends

Charts automatically update based on database entries.

---

# 🧪 Example API Request

Submit issue:

```
POST /api/issues
```

Body:

```
{
"description": "Street light broken near hospital",
"location_name": "Downtown District",
"lat": 37.7749,
"lng": -122.4194
}
```

Response:

```
{
"message": "Issue created",
"predicted_type": "Electricity"
}
```

---

# 🌍 Deployment(In Work)

 Deployment stack:

Frontend:

* Vercel

Backend:

* Render

Database:

* Neon PostgreSQL

---

# 📌 Future Improvements

* Real-time complaint heatmap
* Admin dashboard for issue resolution
* Live AI classification preview while typing
* Notification system
* Department routing automation

---

# 👨‍💻 Contributors

1)Dheeraj Soni
2)Suryansh Chandel(Leader)
3)Harsh Choudhary
4)Agrim Gupta
