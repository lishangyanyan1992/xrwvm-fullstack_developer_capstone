# Best Cars Dealership - Fullstack Developer Capstone

## Project Overview

**Best Cars Dealership** is a full-stack web application built as part of the IBM Full-Stack Software Developer Professional Certificate capstone project.

The application allows users to browse car dealerships across the United States, read customer reviews, and post their own reviews after logging in. Reviews are analyzed for sentiment (positive, negative, or neutral) using a dedicated microservice.

## Features

- **Home Page** – Browse all car dealerships; filter by US state
- **About Us Page** – Meet the team behind Best Cars Dealership
- **Contact Us Page** – Find dealership contact information
- **User Authentication** – Register, login, and logout
- **Dealer Details** – View individual dealer info and customer reviews
- **Post Reviews** – Authenticated users can submit reviews for a dealership
- **Sentiment Analysis** – Reviews are automatically analyzed for sentiment

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React 18, React Router, Bootstrap |
| Backend (API) | Django, Python |
| Database Backend | Node.js, Express, MongoDB |
| Sentiment Analysis | Flask, NLTK (VADER) |
| Containerization | Docker, Docker Compose |
| Orchestration | Kubernetes |
| CI/CD | GitHub Actions |

## Project Structure

```
xrwvm-fullstack_developer_capstone/
├── server/
│   ├── djangoapp/          # Django application (models, views, APIs)
│   │   └── microservices/  # Flask sentiment analysis service
│   ├── djangoproj/         # Django project configuration
│   ├── frontend/           # React frontend application
│   │   ├── src/            # React components
│   │   └── static/         # Static HTML pages (About, Contact, Home)
│   ├── database/           # Node.js + MongoDB backend service
│   ├── Dockerfile
│   └── deployment.yaml
├── .github/workflows/      # GitHub Actions CI/CD
└── README.md
```

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/djangoapp/get_dealers` | Get all dealerships |
| GET | `/djangoapp/get_dealers/<state>` | Get dealers by state |
| GET | `/djangoapp/dealer/<id>` | Get dealer by ID |
| GET | `/djangoapp/reviews/dealer/<id>` | Get reviews for a dealer |
| GET | `/djangoapp/get_cars` | Get all car makes and models |
| POST | `/djangoapp/login` | User login |
| GET | `/djangoapp/logout` | User logout |
| POST | `/djangoapp/register` | User registration |
| POST | `/djangoapp/add_review` | Post a review (authenticated) |

## Running Locally

### Prerequisites
- Python 3.12+
- Node.js 18+
- Docker & Docker Compose
- MongoDB

### Start Services

```bash
# 1. Start MongoDB + Node.js backend
cd server/database
docker-compose up -d

# 2. Start Flask sentiment analyzer
cd server/djangoapp/microservices
pip install -r requirements.txt
python app.py &

# 3. Start Django server
cd server
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

The app will be available at `http://localhost:8000`

## GitHub Repository

[https://github.com/lishangyanyan1992/xrwvm-fullstack_developer_capstone](https://github.com/lishangyanyan1992/xrwvm-fullstack_developer_capstone)
