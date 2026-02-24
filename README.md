This project demonstrates containerization, deployment, and CI/CD setup of a full-stack MEAN application using Docker, Docker Compose, Nginx, and GitHub Actions.

## Architecture
Client → Nginx (Reverse Proxy) → Frontend Container → Backend Container → MongoDB Container

## Technologies Used
- MongoDB
- Docker & Docker Compose
- Nginx Reverse Proxy
- AWS EC2 (Ubuntu)
- GitHub Actions (CI/CD)

## Docker Setup

### Build Images Locally

Backend:
docker build -t <username>/backend ./backend

Frontend:
docker build -t <username>/frontend ./frontend

## Deployment On AWS EC2
1. Launch Ubuntu EC2 instance
2. Install Docker and Docker Compose
3. Clone repository
4. Run:

docker-compose up -d

5. Access application:
http://<EC2-Public-IP>:3000

## Database
MongoDB is deployed using the official Docker image within Docker Compose.

## Nginx Configuration
Nginx is configured as a reverse proxy to expose the application on port 80.

Frontend → http://server-ip/
Backend API → http://server-ip/api

## CI/CD Pipeline
GitHub Actions workflow:

- Trigger: Push to main branch
- Builds Docker images
- Pushes images to Docker Hub
