# 🚗 CarConnect - Full Stack Dealership Platform

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Python](https://img.shields.io/badge/Python-3.12-blue.svg)](https://www.python.org/)
[![Django](https://img.shields.io/badge/Django-6.0-green.svg)](https://www.djangoproject.com/)
[![React](https://img.shields.io/badge/React-18.2-blue.svg)](https://reactjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-Express-green.svg)](https://nodejs.org/)
[![Docker](https://img.shields.io/badge/Docker-Ready-blue.svg)](https://www.docker.com/)

> **IBM Full Stack Developer Capstone Project** - A comprehensive automobile dealership management and review platform demonstrating full-stack development expertise.

**Repository:** [IBM-fullstack_developer_capstone](https://github.com/JACS002/IBM-fullstack_developer_capstone)  
**Project Name:** CarConnect

---

## 📋 Table of Contents

- [About](#about)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Architecture](#architecture)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [API Documentation](#api-documentation)
- [Deployment](#deployment)
- [Skills Demonstrated](#skills-demonstrated)
- [Screenshots](#screenshots)
- [License](#license)
- [Acknowledgments](#acknowledgments)

---

## 🎯 About

**CarConnect** is a modern, full-stack web application built as the capstone project for the **IBM Full Stack Developer Professional Certificate**. This platform enables users to browse automobile dealerships across different states, view detailed dealer information, read customer reviews with sentiment analysis, and submit their own reviews after purchasing vehicles.

The application showcases enterprise-level software development practices including microservices architecture, containerization, CI/CD pipelines, and cloud-native deployment strategies.

---

## ✨ Features

### Core Functionality

- 🏢 **Dealership Management** - Browse and search dealerships by state
- 📍 **Location-Based Search** - Filter dealerships by geographic location
- ⭐ **Review System** - Read and write authenticated customer reviews
- 🤖 **Sentiment Analysis** - AI-powered sentiment detection for reviews
- 🚙 **Vehicle Inventory** - View available car makes and models
- 👤 **User Authentication** - Secure registration and login system
- 📊 **Dynamic Dashboard** - Real-time data visualization

### Technical Features

- 🔐 **JWT Authentication** - Secure token-based authentication
- 📱 **Responsive Design** - Mobile-first, fully responsive UI
- 🐳 **Containerized** - Docker-ready for easy deployment
- 🔄 **RESTful APIs** - Clean, well-documented API endpoints
- 🧪 **Automated Testing** - Comprehensive test coverage
- 🚀 **CI/CD Pipeline** - Automated linting and deployment workflows
- 💾 **Data Persistence** - PostgreSQL database integration

---

## 🛠️ Technology Stack

### Frontend

- **React 18.2** - Modern component-based UI framework
- **React Router v6** - Client-side routing
- **Bootstrap** - Responsive styling framework
- **JavaScript ES6+** - Modern JavaScript features

### Backend

- **Django 6.0** - Python web framework
- **Django REST Framework** - API development
- **Gunicorn** - WSGI HTTP server
- **Python 3.12** - Core backend language

### Microservices

- **Node.js + Express** - Dealership and review services
- **IBM Watson NLU** - Natural Language Understanding for sentiment analysis
- **MongoDB** - NoSQL database for dealership data

### Database

- **SQLite** - Development database
- **PostgreSQL** - Production database (cloud deployment)

### DevOps & Tools

- **Docker** - Containerization
- **GitHub Actions** - CI/CD automation
- **Git** - Version control
- **Flake8** - Python linting
- **JSHint** - JavaScript linting

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                        Client Layer                          │
│                    (React + Bootstrap)                       │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────┐
│                    Django Application                        │
│              (REST API + Authentication)                     │
└───┬──────────────────┬─────────────────┬───────────────────┘
    │                  │                 │
    ▼                  ▼                 ▼
┌──────────┐    ┌─────────────┐    ┌──────────────────┐
│ SQLite/  │    │   Node.js   │    │  IBM Watson NLU  │
│PostgreSQL│    │Microservices│    │(Sentiment Analyzer)
└──────────┘    └──────┬──────┘    └──────────────────┘
                       │
                       ▼
                ┌──────────────┐
                │   MongoDB    │
                │(Dealerships  │
                │ & Reviews)   │
                └──────────────┘
```

---

## 📁 Project Structure

```
IBM-fullstack_developer_capstone/
├── .github/
│   └── workflows/
│       └── main.yml              # CI/CD pipeline configuration
├── server/
│   ├── database/                 # Node.js microservices
│   │   ├── app.js               # Express server
│   │   ├── dealership.js        # Dealership endpoints
│   │   ├── inventory.js         # Inventory management
│   │   ├── review.js            # Review endpoints
│   │   ├── Dockerfile           # Microservices container
│   │   └── data/                # JSON data files
│   ├── djangoapp/               # Django application
│   │   ├── models.py            # Data models
│   │   ├── views.py             # API views
│   │   ├── urls.py              # URL routing
│   │   ├── restapis.py          # External API integration
│   │   ├── admin.py             # Admin configuration
│   │   └── microservices/       # Sentiment analysis service
│   ├── djangoproj/              # Django project settings
│   │   ├── settings.py          # Configuration
│   │   └── urls.py              # Main URL routing
│   ├── frontend/                # React application
│   │   ├── src/
│   │   │   ├── components/      # React components
│   │   │   ├── App.js           # Main app component
│   │   │   └── index.js         # Entry point
│   │   ├── public/              # Static files
│   │   └── build/               # Production build
│   ├── Dockerfile               # Django app container
│   ├── entrypoint.sh            # Container startup script
│   ├── requirements.txt         # Python dependencies
│   ├── manage.py                # Django management
│   └── db.sqlite3               # SQLite database
├── .flake8                      # Python linting config
└── README.md                    # Project documentation
```

---

## 🚀 Installation

### Prerequisites

- Python 3.12+
- Node.js 14+
- Docker (optional)
- Git

### Local Development Setup

#### 1. Clone the Repository

```bash
git clone https://github.com/JACS002/IBM-fullstack_developer_capstone.git
cd IBM-fullstack_developer_capstone
```

#### 2. Backend Setup (Django)

```bash
cd server

# Create virtual environment
python -m venv djangoenv

# Activate virtual environment
# Windows
.\djangoenv\Scripts\activate
# Linux/Mac
source djangoenv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run migrations
python manage.py makemigrations
python manage.py migrate

# Create superuser (optional)
python manage.py createsuperuser

# Start Django server
python manage.py runserver
```

#### 3. Frontend Setup (React)

```bash
cd server/frontend

# Install dependencies
npm install

# Build for production
npm run build

# Or run development server
npm start
```

#### 4. Microservices Setup (Node.js)

```bash
cd server/database

# Install dependencies
npm install

# Start microservices
npm start
```

#### 5. Sentiment Analysis Service

```bash
cd server/djangoapp/microservices

# Install dependencies
pip install -r requirements.txt

# Start sentiment analyzer
python app.py
```

---

## 🐳 Docker Deployment

### Build and Run with Docker

```bash
# Build the image
docker build -t carconnect-app ./server

# Run the container
docker run -p 8000:8000 carconnect-app

# Or use docker-compose (if configured)
docker-compose up
```

---

## 💻 Usage

### Access the Application

- **Frontend:** http://localhost:3000
- **Django Admin:** http://localhost:8000/admin
- **API Endpoints:** http://localhost:8000/djangoapp
- **Microservices:** http://localhost:3030

### User Workflows

#### Browse Dealerships

1. Navigate to the home page
2. Click "Dealerships" to view all dealers
3. Use state filter to narrow down results
4. Click on a dealer to view details

#### Submit a Review

1. Register/Login to your account
2. Navigate to a dealership detail page
3. Click "Write a Review"
4. Fill in vehicle details and review text
5. Submit - sentiment will be automatically analyzed

#### View Reviews

- Reviews display with sentiment indicators (positive/neutral/negative)
- Filter by dealership or view all reviews
- See reviewer name, vehicle, and purchase date

---

## 📡 API Documentation

### Authentication Endpoints

```
POST /djangoapp/register      - Register new user
POST /djangoapp/login         - User login
GET  /djangoapp/logout        - User logout
```

### Dealership Endpoints

```
GET  /djangoapp/get_dealers                - Get all dealerships
GET  /djangoapp/get_dealers/<state>        - Get dealers by state
GET  /djangoapp/dealer/<dealer_id>         - Get dealer details
```

### Review Endpoints

```
GET  /djangoapp/reviews/dealer/<dealer_id> - Get dealer reviews
POST /djangoapp/add_review                 - Submit new review
```

### Vehicle Endpoints

```
GET  /djangoapp/get_cars                   - Get all car models
```

---

## 🎓 Skills Demonstrated

This capstone project demonstrates proficiency in:

### Frontend Development

✅ React.js component architecture  
✅ State management and hooks  
✅ React Router for SPA navigation  
✅ Responsive UI/UX design  
✅ API integration and async operations

### Backend Development

✅ Django REST Framework  
✅ RESTful API design  
✅ Database modeling and ORM  
✅ User authentication & authorization  
✅ CORS and security configuration

### Microservices

✅ Node.js/Express server development  
✅ MongoDB integration  
✅ Service-oriented architecture  
✅ External API integration (IBM Watson)

### DevOps & Cloud

✅ Docker containerization  
✅ CI/CD pipeline setup (GitHub Actions)  
✅ Code quality automation (linting)  
✅ Version control with Git  
✅ Environment configuration management

### Software Engineering

✅ Clean code principles  
✅ PEP 8 and ESLint compliance  
✅ Project documentation  
✅ Agile development practices  
✅ Problem-solving and debugging

---

## 📝 License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- **IBM Skills Network** - For providing the comprehensive Full Stack Developer course
- **Coursera** - Educational platform hosting the certificate program
- **IBM Watson** - Natural Language Understanding API for sentiment analysis
- **Open Source Community** - For the amazing tools and frameworks used in this project

---

## 👨‍💻 Author

**JACS002**

- GitHub: [@JACS002](https://github.com/JACS002)
- Project: [CarConnect - IBM Full Stack Capstone](https://github.com/JACS002/IBM-fullstack_developer_capstone)

---

## 🎓 Certificate

This project was developed as the capstone requirement for the **IBM Full Stack Software Developer Professional Certificate** program, demonstrating comprehensive skills in modern web development, cloud technologies, and software engineering best practices.

---

<div align="center">
  <strong>⭐ If you find this project helpful, please consider giving it a star! ⭐</strong>
</div>
