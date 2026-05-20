## Project Overview
A fully containerized, cloud-native e-commerce platform built with microservices architecture, Docker, Kubernetes, Jenkins, and GitHub Actions CI/CD pipelines.


## Team Members
| Name | Roll Number | Role |
|------|-------------|------|
| Iffat Batool | FA23-BCS-067 | Team Lead |
| Ahmad Mustafa | FA23-BCS-002 | Member |

---

## Repository
- **GitHub:** https://github.com/iffatbatool067/microservices-ecommerce
- **Docker Hub:** https://hub.docker.com/r/iffatbatool/shopcloud-frontend

---

## Folder Structure
microservices-ecommerce/
├── .github/
│   └── workflows/
│       ├── ci-dev.yml           # CI pipeline for develop branch
│       ├── cd-staging.yml       # CD pipeline for staging branch
│       └── cd-production.yml    # CD pipeline for production branch
├── src/
│   ├── frontend/
│   │   ├── index.html           # Home Page
│   │   ├── user.html            # User Service Page
│   │   ├── products.html        # Product Service Page
│   │   ├── orders.html          # Order Service Page
│   │   └── notifications.html   # Notification Service Page
│   ├── user-service/
│   │   └── index.js             # User microservice
│   ├── product-service/
│   │   └── index.js             # Product microservice
│   ├── order-service/
│   │   └── index.js             # Order microservice
│   └── notification-service/
│       └── index.js             # Notification microservice
├── k8s/
│   ├── frontend-deployment.yaml      # Kubernetes - Frontend
│   ├── user-deployment.yaml          # Kubernetes - User Service
│   ├── product-deployment.yaml       # Kubernetes - Product Service
│   ├── order-deployment.yaml         # Kubernetes - Order Service
│   └── notification-deployment.yaml  # Kubernetes - Notification Service
├── Dockerfile                   # Docker config for frontend
├── Jenkinsfile                  # Jenkins declarative pipeline
├── .gitignore                   # Git ignore rules
├── .dockerignore                # Docker ignore rules
└── README.md                    # Project documentation

---

## Microservices
| Service | Port | Description |
|---------|------|-------------|
| Frontend | 80 | HTML/CSS Dashboard — 5 pages |
| User Service | 3001 | JWT Auth, Registration, Login |
| Product Service | 3002 | Product Catalog, CRUD APIs |
| Order Service | 3003 | Order Processing, Tracking |
| Notification Service | 3004 | Email & In-App Notifications |

---

## Branch Strategy (Git Flow)
| Branch | Purpose |
|--------|---------|
| main | Production — stable releases |
| staging | QA/Testing environment |
| develop | Active development |
| production | Final production deployment |

---

## CI/CD Pipeline
Checkout → Build → Test → Docker Build → Push → Deploy → Notify
- **ci-dev.yml** — HTML linting + Docker build test (develop branch)
- **cd-staging.yml** — Build + Push staging image (staging branch)
- **cd-production.yml** — Build + Push production image (main branch)

---

## Jenkins Pipeline Stages
Checkout → Build & Test → Docker Build → Docker Push → Deploy to Kubernetes → Notification

---

## How to Run Locally

### Using Docker
```bash
docker pull iffatbatool/shopcloud-frontend:latest
docker run -d -p 8080:80 --name shopcloud iffatbatool/shopcloud-frontend:latest
```
Open browser: http://localhost:8080

### Using Python Server
```bash
cd src/frontend
python3 -m http.server 8080
```

---

## Kubernetes Deployment
```bash
kubectl apply -f k8s/frontend-deployment.yaml
kubectl apply -f k8s/user-deployment.yaml
kubectl apply -f k8s/product-deployment.yaml
kubectl apply -f k8s/order-deployment.yaml
kubectl apply -f k8s/notification-deployment.yaml
```

---

## GitHub Environments
| Environment | Branch | Type |
|-------------|--------|------|
| development | develop | CI — Build & Test |
| staging | staging | CD — Deploy to QA |
| production | main | CD — Deploy to Production |

---

## Technologies Used
- **Docker** — Containerization
- **Kubernetes** — Orchestration
- **GitHub Actions** — CI/CD Automation
- **Jenkins** — Declarative Pipeline
- **Nginx** — Web Server
- **Git Flow** — Branching Strategy
- **JWT** — Authentication
- **RabbitMQ** — Message Queue

