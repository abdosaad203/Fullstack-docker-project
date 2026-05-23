# Fullstack Dockerized Application

A complete full-stack containerized application using:

* React (Frontend)
* Go (Backend)
* PostgreSQL
* Redis
* Nginx Reverse Proxy
* Docker & Docker Compose

The project was originally based on exercises from:

https://devopswithdocker.com/

---

# Project Architecture

The application consists of:

* Frontend application built with React
* Backend API built with Go
* PostgreSQL database
* Redis in-memory database
* Nginx reverse proxy
* Docker Compose orchestration

Nginx routes requests as follows:

* `/` → Frontend container
* `/api` → Backend container

---

# Features

* Dockerized frontend and backend
* Multi-stage Docker builds
* Non-root containers
* Nginx reverse proxy
* PostgreSQL integration
* Redis integration
* Docker Compose orchestration
* Health checks
* Optimized image sizes
* AWS EC2 deployment

---

# Tech Stack

* React
* Go (Gin Framework)
* PostgreSQL
* Redis
* Nginx
* Docker
* Docker Compose
* AWS EC2

---

# Project Structure

```bash
.
├── backend
├── frontend
├── app-screeshots
├── docker-compose.yml
└── README.md
```

---

# Running the Project

## Prerequisites

Install:

* Docker Engine
* Docker Compose

Docker installation:

https://docs.docker.com/engine/install/

Docker Compose installation:

https://docs.docker.com/compose/install/

---

# Run Locally

```bash
docker compose up --build
```

Check running containers:

```bash
docker compose ps
```

Stop containers:

```bash
docker compose down
```

---

# Access the Application

Frontend:

```bash
http://localhost:5000
```

Backend Health Check:

```bash
http://localhost:8080/ping
```

---

# Docker Hub Images

Frontend Image:

```bash
docker pull abdosaad0/frontend-app:v1
```

Backend Image:

```bash
docker pull abdosaad0/backend-app:v1
```

---

# Deployment

The project was successfully deployed on an AWS EC2 instance using Docker Compose.

Deployment includes:

* Pulling Docker images from Docker Hub
* Running all services using Docker Compose
* Exposing the application through EC2 public IP

---

# Project Diagram

![Project Diagram](./app-screeshots/app-diagram.png)

---

# Complete Project Screenshot

![Complete Project Screenshot](./app-screeshots/complete-project.png)
