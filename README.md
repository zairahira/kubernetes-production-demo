# Kubernetes Production Deployment Demo

## Project Overview
This project demonstrates a production-ready Nginx deployment on Kubernetes, applying real-world operational best practices from my 4+ years of managing 24/7 critical Linux production environments.

### Key Features Implemented
- **Multi-replica Deployment** (3 replicas for high availability)
- **Resource Requests & Limits** (CPU and Memory) - prevents resource starvation
- **Liveness & Readiness Probes** - ensures application health and proper traffic routing
- **NodePort Service** for external access
- Clean labeling and best-practice configuration

### Technologies Used
- Kubernetes (kind cluster)
- Docker (nginx:alpine image)
- kubectl

### Deployment Commands

```bash
# Create the cluster
kind create cluster --name production-demo

# Apply the deployment
kubectl apply -f production-deployment.yaml

# Check status
kubectl get all
```

### What I Learned / Production Mindset

- Applied same stability principles I used in telco production support (monitoring application health, resource management, and high availability)
- Focused on making the application resilient rather than just "running"
- Used probes to simulate real production incident prevention

### How to Access the Application
```bash
kubectl port-forward svc/nginx-production-service 8080:80
```
Then open: http://localhost:8080

<img width="921" height="466" alt="image" src="https://github.com/user-attachments/assets/026ffaa7-836f-4fc5-9d3b-4038f7517bd8" />
