# Kubernetes Manifests

### 📌 Overview
This repository defines a complete Kubernetes stack consisting of:

**1. Database Layer**
- MySQL running as **StatefulSet** with **Headless service**
- Storage: **AWS EBS gp3**
- Secure credentials via **Secret**

**2. Backend Layer**
- Backend app is running as **Deployment**
- Connects to MySQL via **ClusterIP service**
- Uses **EFS PVC** for shared data
- Environment from **ConfigMap & Secret**

**3. Frontend Layer**
- Frontend app is running as **Deployment**
- Connects to service via **LoadBalancer**
- Config driven via **ConfigMap**

**4. Ingress**
- Internal communication via **ClusterIP**
- External access via **AWS ALB Ingress**
- Path based routing:
  - `/` → frontend
  - `/api` → backend
  - `admin.example.com/api` → admin service

**5. Storage**
- MySQL → **gp3 (RWO)**
- Application → **EFS (RWX shared)**
