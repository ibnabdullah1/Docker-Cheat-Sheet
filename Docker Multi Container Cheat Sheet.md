# 🐳 Docker Multi-Container Cheat Sheet

## 🔗 Docker Network

```bash
docker network create ts-docker-net
```

---

## 🍃 MongoDB Container (No Dockerfile Needed)

> Pulls directly from DockerHub

```bash
docker run --name mongodb \
  --rm \
  -v ts-docker-db:/data/db \
  --network ts-docker-net \
  -e MONGO_INITDB_ROOT_USERNAME=ts-docker \
  -e MONGO_INITDB_ROOT_PASSWORD=ts-docker \
  mongo
```

---

## 🚀 Node.js/Express Backend

### 🔨 Build Backend Image

```bash
docker build -t ts-docker-backend:v5 .
```

### 🧱 Run Backend Container

```bash
docker run --name ts-docker-backend-container \
  --rm \
  --network ts-docker-net \
  --env-file .env \
  -w /app \
  -v ts-docker-logs:/app/logs \
  -v "$(pwd)":/app \
  -v /app/node_modules \
  -p 5000:5000 \
  ts-docker-backend:v5
```

📄 [Dockerfile for Node.js Backend](https://www.notion.so/Dockerfile-Nodejs-1fa8dff2056281eb8c0cc72d0b39d2ae?pvs=21)

---

## ⚛️ Next.js / React Frontend

### 🔨 Build Frontend Image

```bash
docker build -t ts-docker-frontend:v5 .
```

### 🧱 Run Frontend Container

```bash
docker run --name ts-docker-frontend-container \
  --rm \
  -p 3000:3000 \
  --env-file .env.local \
  -w /app \
  -v "$(pwd)":/app \
  -v /app/node_modules \
  --network ts-docker-net \
  -e WATCHPACK_POLLING=true \
  ts-docker-frontend:v5
```

📄 [Dockerfile for Next.js/React Frontend](https://www.notion.so/Dockerfile-NextJS-React-Frontend-1fa8dff2056281aaba18dc9cc43cd006?pvs=21)
