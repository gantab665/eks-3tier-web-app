# 🚀 EKS 3-Tier Web Application

This repository contains a **3-tier web application** deployed on **AWS EKS** using **Docker** and **Kubernetes**.  
The project is built for **hands-on learning** and to demonstrate a **real-world Kubernetes deployment**.

---

## 🧱 Architecture Overview

The application follows a classic **3-tier architecture**:

User
|
v
AWS LoadBalancer (Frontend Service)
|
v
Frontend (React + NGINX)
|
v
Backend Service (Node.js / Express)
|
v
MongoDB (ClusterIP Service)


---

## 🛠️ Tech Stack

- **Frontend**: React, NGINX
- **Backend**: Node.js, Express
- **Database**: MongoDB
- **Containerization**: Docker
- **Orchestration**: Kubernetes (EKS)
- **Cloud Provider**: AWS
- **Container Registry**: Amazon ECR Public

---

## 📁 Project Structure



eks-3tier-web-app/
│
├── frontend/
│ ├── Dockerfile
│ ├── nginx.conf
│ ├── public/
│ └── src/
│
├── backend/
│ ├── Dockerfile
│ ├── package.json
│ └── server.js
│
├── k8s_manifests/
│ ├── frontend/
│ │ ├── frontend-deployment.yaml
│ │ └── frontend-service.yaml
│ │
│ ├── backend/
│ │ ├── backend-deployment.yaml
│ │ └── backend-service.yaml
│ │
│ └── mongo_v1/
│ ├── deploy.yaml
│ ├── service.yaml
│ └── secrets.yaml
│
└── README.md


---

## 🚀 Application Flow

1. User accesses the application via an **AWS LoadBalancer URL**
2. Traffic is routed to the **frontend React app**
3. NGINX proxies `/api` requests to the backend service
4. Backend communicates with MongoDB using Kubernetes service discovery
5. Response is returned and displayed in the UI

---

## 📦 Docker Images

- Frontend and backend are containerized using **multi-stage Docker builds**
- Images are pushed to **Amazon ECR Public**
- Kubernetes pulls images directly from ECR

---

## ☸️ Kubernetes Deployment

- **MongoDB**
  - Deployment + ClusterIP Service
- **Backend**
  - Deployment + ClusterIP Service
- **Frontend**
  - Deployment + LoadBalancer Service
- All services run inside a dedicated Kubernetes namespace

---

## ✅ Working Features

- Kubernetes internal DNS-based service discovery
- NGINX reverse proxy for backend API
- React frontend fetching live backend data
- MongoDB running inside the cluster
- Fully containerized and deployed on AWS EKS

---

## ⚠️ Notes

- This project is **for personal learning and portfolio use**
- Health checks, autoscaling, and ingress controllers are intentionally omitted
- Security hardening (IAM roles, TLS, Secrets Manager) can be added later

---

## 🧑‍💻 Author

**Bhavya Reddy Ganta**  
Personal AWS EKS & Kubernetes learning project




