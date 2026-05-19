# ShopCloud - Cloud-Native E-Commerce Platform

## Project Overview
A microservices-based e-commerce platform built with Docker, Kubernetes, and CI/CD pipelines for COMSATS University DevOps Final Project.

## Group Repository
https://github.com/iffatbatool067/microservices-ecommerce

## Docker Hub
https://hub.docker.com/r/iffatbatool/shopcloud-frontend

## Branch Strategy (Git Flow)
| Branch | Purpose |
|--------|---------|
| main | Production |
| staging | QA/Testing |
| develop | Development |

## Microservices
| Service | Port | Description |
|---------|------|-------------|
| Frontend | 80 | HTML/CSS Dashboard |
| User Service | 3001 | JWT Auth & Profiles |
| Product Service | 3002 | Product Catalog |
| Order Service | 3003 | Order Processing |
| Notification Service | 3004 | Email Alerts |

## How to Run Locally
```bash
docker pull iffatbatool/shopcloud-frontend:latest
docker run -d -p 8080:80 iffatbatool/shopcloud-frontend:latest
```
Open: http://localhost:8080

## CI/CD Pipeline
GitHub Actions automatically:
1. Lints HTML files
2. Builds Docker image
3. Pushes to Docker Hub

## Jenkins Pipeline Stages
1. Checkout
2. Build
3. Test
4. Docker Build
5. Docker Push
6. Deploy
7. Notify

## Kubernetes Deployment
```bash
kubectl apply -f k8s/
```

## Tech Stack
- Docker & Docker Hub
- Kubernetes
- GitHub Actions
- Jenkins
- Nginx

## Reflection
This project gave hands-on experience with containerized microservices, Kubernetes orchestration, and automated CI/CD pipelines. We learned Git Flow collaboration, Docker image management, and enterprise DevOps practices.
