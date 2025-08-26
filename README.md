# Face Recognition Web App (Dockerized)

This repository provides a **Docker Compose setup** for running the complete Face Recognition Web App, including backend, frontend, PostgreSQL, and optional pgAdmin.
All services are pre-built and published on Docker Hub — no need to build anything locally.

---

## 🚀 Quick Start

### 1. Clone this repository

```bash
git clone https://github.com/<your-username>/face-recognition-docker.git
cd face-recognition-docker
```

### 2. Run the app with Docker Compose

```bash
docker compose up -d
```

Docker will automatically pull the required images from Docker Hub.

### 3. Access the services

* **Frontend (UI)** → [http://localhost:5173](http://localhost:5173)
* **Backend API** → [http://localhost:8000](http://localhost:8000)
* **Face Registration Service** → [http://localhost:8001](http://localhost:8001)
* **pgAdmin (Database Admin Tool)** → [http://localhost:5050](http://localhost:5050)

  * Login: `admin@insightface.com` / `admin`
  * Server: `postgres`
  * DB: `insightface_db`

---

## 🛠️ Requirements

* [Docker](https://docs.docker.com/get-docker/)
* [Docker Compose](https://docs.docker.com/compose/)

---

## ⚙️ Configuration

The stack uses default credentials (see `docker-compose.yml`).

* **Postgres** → user: `postgres`, password: `password`
* **Database** → `insightface_db`

You can edit these in the `docker-compose.yml` file before running.

---

## 📦 Services

| Service              | Port | Description                    |
| -------------------- | ---- | ------------------------------ |
| `frontend`           | 5173 | Web frontend (React + Vite)    |
| `backend`            | 8000 | FastAPI backend                |
| `face-registration`  | 8001 | Face registration microservice |
| `postgres`           | 5432 | PostgreSQL database            |
| `pgadmin` (optional) | 5050 | Database admin UI              |

---

## 🛑 Stopping the app

```bash
docker compose down
```

---

## 📥 Updating to a New Version

If new images are published, just run:

```bash
docker compose pull
docker compose up -d
```

---

## 📌 Notes

* No local build required — all images are hosted on Docker Hub under [`meabdullah`](https://hub.docker.com/u/meabdullah).
* This setup is intended for local development & testing. For production, consider using volumes for persistent data and secrets for credentials.
