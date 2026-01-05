# Smart Attendance System (SAS)

A modern, web-based attendance management system using facial recognition technology. This system provides real-time face recognition for automated attendance tracking with a secure admin interface.

![Python](https://img.shields.io/badge/python-3.12+-blue.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-0.120-green)
![Flask](https://img.shields.io/badge/Flask-3.1.2-lightgrey.svg)

---

## 📋 Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [Prerequisites](#prerequisites)
- [Quick Start](#quick-start)
- [Project Structure](#project-structure)
- [Documentation](#documentation)
- [Security](#security)
- [License](#license)

---

## Overview

The Smart Attendance System is a complete attendance management solution that uses facial recognition to automatically track attendance. It consists of two main components:

1. **Backend API** - FastAPI-based facial recognition engine with database management
2. **Frontend Web App** - Flask-based user interface for enrollment and attendance tracking

### Key Features

- 🔐 **Secure Authentication** - JWT-based admin login system
- 👤 **Face Enrollment** - Enroll users via camera capture or images
- 📸 **Real-time Recognition** - Automatic attendance marking using face detection
- 📊 **Live Dashboard** - View attendance records in real-time
- 🚻 **Absent Tracking** - Automatically identifies and marks absent users

---

## Architecture

```
┌─────────────────────────────────────────────────────────┐
│              Smart Attendance System                     │
├─────────────────────────────────────────────────────────┤
│                                                         │
│   ┌─────────────────┐      ┌─────────────────┐          │
│   │   Frontend      │      │   Backend       │          │
│   │   (Flask)       │◄────►│   (FastAPI)     │          │
│   │   Port: 5000    │      │   Port: 8000    │          │
│   └────────┬────────┘      └────────┬────────┘          │
│            │                        │                   │
│            │     REST API           │                   │
│            └────────────────────────┘                   │
│                                                         │
│   ┌─────────────────────────────────────────────┐      │
│   │           SQLite Database                   │      │
│   │    (Stores persons, embeddings, records)    │      │
│   └─────────────────────────────────────────────┘      │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

---

## Prerequisites

- **Python 3.12+** (for backend)
- **Python 3.8+** (for frontend)
- **Git**
- **Webcam** (for real-time attendance and enrollment)
- **Modern browser** with camera support

---

## Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/AhmadNMatar/Smart-Attendance-System.git
cd Smart-Attendance-System
```

### 2. Setup Backend

```bash
cd backend

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Linux/Mac
# OR: venv\Scripts\activate  # Windows

# Install dependencies
pip install -r requirements.txt

# Configure environment
# Create .env file with DATABASE_URL and JWT settings
# (See backend/readme.md for details)

# Start the backend server
uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload
```

### 3. Setup Frontend

```bash
cd frontend

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Linux/Mac
# OR: venv\Scripts\activate  # Windows

# Install dependencies
pip install -r requirement.txt

# Configure environment
# Create .env file with BACKEND_URL
# Example: BACKEND_URL=http://localhost:8000

# Start the frontend server
flask run
```

### 4. Access the Application

- **Frontend**: http://localhost:5000
- **Backend API Docs**: http://localhost:8000/docs
- **Backend ReDoc**: http://localhost:8000/redoc

---

## Project Structure

```
Smart-Attendance-System/
├── README.md                    # This file (high-level overview)
├── backend/                     # FastAPI backend application
│   ├── app/
│   │   ├── main.py              # Application entry point
│   │   ├── config/              # Database configuration
│   │   ├── models/              # SQLModel database models
│   │   ├── cruds/               # Database operations
│   │   ├── routers/             # API endpoints
│   │   └── services/            # Face recognition services
│   ├── requirements.txt         # Python dependencies
│   └── readme.md                # Detailed backend documentation
│
└── frontend/                    # Flask frontend application
    ├── app/
    │   ├── static/              # CSS and JavaScript files
    │   └── templates/           # HTML templates
    ├── requirement.txt          # Python dependencies
    └── README.md                # Detailed frontend documentation
```

---

## Documentation

For detailed information about each component, refer to the dedicated README files:

### Backend Documentation
📄 **[backend/readme.md](backend/readme.md)** - Comprehensive backend guide including:
- Installation and configuration
- API endpoints reference
- Authentication details
- Usage examples

### Frontend Documentation
📄 **[frontend/README.md](frontend/README.md)** - Comprehensive frontend guide including:
- Setup instructions
- User interface usage
- Configuration options
- API integration details

---

## Security

- All endpoints require JWT authentication (except login and signup)
- Passwords are securely hashed using bcrypt
- Admin role verification for sensitive operations
- CORS configured for frontend integration

---

## Tech Stack

### Backend
| Technology | Purpose |
|------------|---------|
| FastAPI | Web framework |
| SQLModel | Database ORM |
| InsightFace | Face recognition |
| ONNX Runtime | ML inference |
| PyJWT | Authentication |
| Uvicorn | ASGI server |

### Frontend
| Technology | Purpose |
|------------|---------|
| Flask | Web framework |
| python-dotenv | Configuration |
| requests | HTTP client |
| HTML/CSS/JS | User interface |

---

## Author

**Ahmad Matar**

- GitHub: [@AhmadNMatar](https://github.com/AhmadNMatar)

---

## Acknowledgments

- [InsightFace](https://github.com/deepinsight/insightface) - Face analysis library
- [FastAPI](https://fastapi.tiangolo.com/) - Excellent Python API framework
- [Flask](https://flask.palletsprojects.com/) - Lightweight web framework

