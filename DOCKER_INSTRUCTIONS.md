# 🐳 Docker Run Instructions – Weather App

This file contains all necessary `docker build` and `docker run` commands to run the **backend** and **frontend** of your weather app without Docker Compose.

---

## 📦 Step 1: Build Images

### 🔧 Backend
```bash
cd server
docker build -t server-app .

## frontend 
cd client
docker build -t weather-app .

## backend container
docker run -d \
  --name backend \
  --env-file .env \
  -p 3000:3000 \
  server-app

##frontend container
docker run -d \
  --name frontend \
  -p 5173:80 \
  weather-app