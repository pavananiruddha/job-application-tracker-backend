# Job Application Tracker – Backend

A Django REST API for tracking job applications with JWT authentication and user-based access control.

This backend allows users to register, authenticate, and manage their own job applications securely.

---

##  Tech Stack

- Python
- Django
- Django REST Framework
- Simple JWT (JWT Authentication)
- PostgreSQL (SQLite for local development)

---

##  Project Structure

```
job-application-tracker-backend/
│
├── accounts/        # Custom user model & authentication
├── jobs/            # Job application CRUD APIs
├── config/          # Project settings & main URLs
├── manage.py
├── requirements.txt
└── .gitignore
```

---

##  Authentication (JWT)

Authentication is handled using JSON Web Tokens.

After login, include the access token in request headers:

```
Authorization: Bearer <access_token>
```

---

##  API Endpoints

### Authentication

| Method | Endpoint | Description |
|------|---------|------------|
| POST | /api/auth/register/ | Register a new user |
| POST | /api/auth/login/ | Obtain access & refresh tokens |
| POST | /api/auth/token/refresh/ | Refresh access token |

### Job Applications

| Method | Endpoint | Description |
|------|---------|------------|
| GET | /api/jobs/ | List logged-in user's job applications |
| POST | /api/jobs/ | Create a new job application |
| GET | /api/jobs/{id}/ | Retrieve a job application |
| PUT | /api/jobs/{id}/ | Update a job application |
| DELETE | /api/jobs/{id}/ | Delete a job application |

Users can only access their own job applications.

---

##  Key Features

- Custom User Model (Email-based login)
- JWT Authentication
- User-level permissions (IsOwner)
- Secure CRUD operations
- Clean RESTful architecture
- Ready for frontend integration

---

##  Local Setup

### Clone the repository

```bash
git clone https://github.com/pavananiruddha/job-application-tracker-backend.git
cd job-application-tracker-backend
```

### Create virtual environment

```bash
python -m venv env
source env/Scripts/activate
```

### Install dependencies

```bash
pip install -r requirements.txt
```

### Run migrations

```bash
python manage.py migrate
```

### Create superuser

```bash
python manage.py createsuperuser
```

### Run server

```bash
python manage.py runserver
```

Server runs at:

```
http://127.0.0.1:8000/
```

---

##  Testing

APIs can be tested using:
- Django REST Framework UI
- Postman
- Any frontend client

---

##  Future Improvements

- Frontend integration (React / Next.js)
- Job analytics dashboard
- Resume upload support
- Email notifications

---

##  Author

**Pavan Aniruddha**  
Backend Developer (Django, REST APIs)
