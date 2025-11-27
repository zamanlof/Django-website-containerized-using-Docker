# Django Website Containerized Using Docker

A Django-powered movies library website UI, containerized using Docker and Gunicorn.  
This project serves as a foundation for a scalable, user-friendly collection of movie titles with basic features for browsing and user management.

---

## Features

- Movie list and detail views for browsing and exploring film information.
- Responsive, clean UI built with Django templates.
- Basic user authentication: register, login, and logout.
- User profiles: avatar, bio, and social links.
- Movie categorization by genres.
- Pagination for movie listings.
- Homepage showing recent and popular movies.
- Admin dashboard for managing movies and users.

---

## Repository

```
git clone https://github.com/zamanlof/Django-website-containerized-using-Docker.git
cd Django-website-containerized-using-Docker
```

---

## Prerequisites

- Docker installed and running.
- Git (to clone the repository).

_No local Python or virtual environment is required; everything runs inside Docker._

---

## 1. Build the Docker image

From the project root:
```
docker build -t movies-website .
```

This will:

- Install Python dependencies from `requirements.txt`.
- Copy the Django project into the image.
- Run `collectstatic` inside the image.

---

## 2. Run the container

Start the container:

```
docker run -d --name movies-app -p 8000:8000 movies-website
```

---

## 3. Access the application

Open in your browser:

```
http://localhost:8000
```

View logs:
```
docker logs -f movies-app
```

---

## Development notes

- Static files are collected into `staticfiles/` inside the container.
- For local development without Docker, you can still create a virtual environment and run:

```
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

