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

**5. Storage**
- MySQL → **gp3 (RWO)**
- Application → **EFS (RWX shared)**


---

### Commands
- [Kubectl Quick Reference](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
- [Docker Commands](https://kubernetes.io/docs/reference/kubectl/docker-cli-to-kubectl/)

### Learning Resources
- [Docker Curriculum](https://docker-curriculum.com/)
- [Kube by Example](https://kubebyexample.com/)
- [Roadmap – DevOps Learning Roadmaps](https://roadmap.sh/)
- [KodeKloud – Hands-on DevOps Labs](https://kodekloud.com)
- [Kubernetes Documentation](https://kubernetes.io/docs/home/)
- [CNCF – Cloud-Native Ecosystem](https://www.cncf.io/)

### Practice & Labs
- [Killer Coda Browser-based scenarios](https://killercoda.com/)
- [Play with Docker - Quick Docker practice](https://training.play-with-docker.com/)
- [Play with Kubernetes - Live K8s clusters](https://labs.play-with-k8s.com/)
- [Sad Servers - Real Linux production issues](https://sadservers.com/)
- [OverTheWire - Linux + security fundamentals](https://overthewire.org/wargames/)
