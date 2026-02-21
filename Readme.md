# 🐳 Twitter Clone - Docker Deployment

This project is a containerized Twitter Clone application deployed using
**Docker** and **Docker Compose**.\
It includes a frontend, backend, and database service running
as separate containers.

------------------------------------------------------------------------

## 🚀 Features

-   Multi-container Docker setup
-   One-command build & run using Docker Compose
-   Environment-based configuration
-   Easy local development & deployment
-   Production-ready container structure

------------------------------------------------------------------------

## 🏗️ Tech Stack

-   Frontend: React.js
-   Backend: Node.js / Express
-   Database: MongoDB / PostgreSQL (update if needed)
-   Containerization: Docker
-   Orchestration: Docker Compose

------------------------------------------------------------------------
## 📦 Project Structure
.
├── Dockerfile
├── docker-compose.yaml
├── package.json
├── src/
├── README.md


## ⚙️ Prerequisites

Make sure you have installed:

-   Docker
-   Docker Compose

Check installation:

docker --version docker compose version

------------------------------------------------------------------------

## 🐳 Running the Application with Docker

### 1️⃣ Clone the repository

git clone https://github.com/robinvatshr08/SocialSphereD.git

------------------------------------------------------------------------

### 2️⃣ Build and start containers

docker compose up --build

This will: - Build images for frontend & backend - Create containers -
Start the full application

------------------------------------------------------------------------

### 3️⃣ Run in background (detached mode)

docker compose up -d --build

------------------------------------------------------------------------

### 4️⃣ Stop containers

docker compose down

------------------------------------------------------------------------

## 🔍 Check Running Containers

docker ps

------------------------------------------------------------------------

## 🧱 Rebuild Containers (No Cache)

docker compose build --no-cache

------------------------------------------------------------------------

## 🐞 View Logs

docker compose logs -f

For specific service:

docker compose logs backend

------------------------------------------------------------------------

## 🌐 Access the Application

-   Frontend: http://localhost:3003\

(Adjust ports based on your setup)

------------------------------------------------------------------------

## 🔐 Environment Variables

MONGO_URL=mongodb://mongo:27017/mydb


------------------------------------------------------------------------

## 🧹 Clean Docker System (Optional)

docker system prune -a

------------------------------------------------------------------------

## Running Without Docker Compose (Manual Deployment)

This method shows how containers communicate in real DevOps environments.

1️⃣ Build application image
docker build -t robinvats/twitter-app .

2️⃣ Create Docker network
docker network create twitter-net

3️⃣ Run MongoDB container
docker run -d \
  --name mongo \
  --network twitter-net \
  -p 27017:27017 \
  -v mongo_data:/data/db \
  mongo:6

  This creates:
    Mongo container
    Persistent storage volume
    Exposed DB port

4️⃣ Run backend container

docker run -d \
  --name node_app \
  --network twitter-net \
  -p 3003:3003 \
  -e MONGO_URL=mongodb://mongo:27017/mydb \
  robinvats/twitter-app

Docker DNS allows backend to reach Mongo using hostname mongo.


🌐 Access Application
    Backend API → http://localhost:3003
    MongoDB → mongodb://localhost:27017 

## 📦 Future Improvements

-   CI/CD pipeline integration
-   Push images to AWS ECR
-   Kubernetes deployment
-   Nginx reverse proxy setup
-   Production environment configs

------------------------------------------------------------------------

## 👨‍💻 Author

**Robin Vats**\
DevOps & Cloud Enthusiast

GitHub: https://github.com/robinvatshr08/SocialSphereD.git
LinkedIn: www.linkedin.com/in/robin-vats-hr08

