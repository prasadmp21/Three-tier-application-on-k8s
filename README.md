#  Three-Tier Application Deployment on Kubernetes

![Kubernetes](https://img.shields.io/badge/Kubernetes-Deployment-blue?logo=kubernetes)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue?logo=docker)
![React](https://img.shields.io/badge/Frontend-React-61DAFB?logo=react)
![Node.js](https://img.shields.io/badge/Backend-Node.js-339933?logo=node.js)
![MongoDB](https://img.shields.io/badge/Database-MongoDB-47A248?logo=mongodb)

---

##  Overview

This project demonstrates a **production-style deployment** of a **3-tier application** on Kubernetes.

It includes:

* Docker-based containerization
* Kubernetes deployments & services
* ConfigMaps & Secrets management
* Persistent storage with volumes

---

##  Architecture Diagram

```
          ┌───────────────┐
          │   Frontend    │
          │   (React)     │
          └──────┬────────┘
                 │
                 ▼
          ┌───────────────┐
          │    Backend    │
          │   (Node.js)   │
          └──────┬────────┘
                 │
                 ▼
          ┌───────────────┐
          │   Database    │
          │   (MongoDB)   │
          └───────────────┘

All components are deployed as Kubernetes Pods and exposed via Services.
```

---

##  Project Structure

```
.
├── frontend/                  
├── backend/                  
├── backend.yaml              
├── backend-service.yaml      
├── frontend.yaml             
├── frontend-service.yaml     
├── mongodb.yaml              
├── mongodb-service.yaml      
├── configmap.yaml            
├── secret.yaml               
├── volume.yaml               
├── mount.yaml                
├── namespace.yaml            
├── .env                      
```

---

##  Tech Stack

* Docker
* Kubernetes
* React
* Node.js
* MongoDB

---

##  Deployment Steps

### 1. Clone Repository

```
git clone https://github.com/prasadmp21/three-tier-application-on-k8s.git
cd three-tier-application-on-k8s
```

### 2. Create Namespace

```
kubectl apply -f namespace.yaml
```

### 3. Apply Configurations

```
kubectl apply -f configmap.yaml
kubectl apply -f secret.yaml
```

### 4. Setup Storage

```
kubectl apply -f volume.yaml
kubectl apply -f mount.yaml
```

### 5. Deploy MongoDB

```
kubectl apply -f mongodb.yaml
kubectl apply -f mongodb-service.yaml
```

### 6. Deploy Backend

```
kubectl apply -f backend.yaml
kubectl apply -f backend-service.yaml
```

### 7. Deploy Frontend

```
kubectl apply -f frontend.yaml
kubectl apply -f frontend-service.yaml
```

---

##  Verify Deployment

```
kubectl get all -n <your-namespace>
```

---

##  Access Application

For Minikube:

```
minikube service frontend-service -n <your-namespace>
```

---

##  Key Features

* Fully containerized application
* Kubernetes-based orchestration
* Secure configuration using Secrets
* Scalable architecture
* Persistent data storage

---

##  Future Improvements

* Add Ingress Controller
* CI/CD pipeline (GitHub Actions / Jenkins)
* Monitoring (Prometheus + Grafana)
* Logging (ELK Stack)

---

