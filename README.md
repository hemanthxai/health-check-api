# Health Check API – Docker & Kubernetes (Local Setup)

## Overview
A simple Flask-based Health Check API containerized using Docker and deployed on a local Kubernetes cluster.

## Endpoints
- /health  → Returns application health
- /version → Returns application version

## Tech Stack
- Python (Flask)
- Docker
- Kubernetes (Minikube / Kind / You can choose KaaS if you prefer)

## How to Run

### Build Docker Image
docker build -t health-check-api:1.0 .

### Load Image into Kubernetes
For Minikube:
minikube image load health-check-api:1.0

For Kind:
kind load docker-image health-check-api:1.0

### Deploy to Kubernetes
kubectl apply -f k8s/

### Verify
kubectl get pods
kubectl get svc

### Access Application
curl http://localhost:30007/health
curl http://localhost:30007/version

