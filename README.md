# Full-Stack App Deployment with Kubernetes and Minikube

For the detailed article, refer to:  
👉 [https://www.swtestacademy.com/deploy-full-stack-application-in-kubernetes/](https://www.swtestacademy.com/deploy-full-stack-application-in-kubernetes/)

---

## Instructions

### 1. Create Backend Image
```bash
cd backend
docker build -t backend .
```

### 2. Create Frontend Image
```bash
cd ../frontend
docker build -t frontend .
```

### 3. Deploy Kubernetes Resources
```bash
cd ../k8s
kubectl apply -f database.yaml
kubectl apply -f backend.yaml
kubectl apply -f frontend.yaml
```
### 4. Access the Application
```bash
minikube service react-service
```
### Project Structure
```
fullstackapp/
├── backend/
│   ├── Dockerfile
│   ├── main.py
│   └── requirements.txt
├── frontend/
│   ├── Dockerfile
│   └── src/
├── database/
│   ├── Dockerfile
│   └── CreateDB.sql
└── k8s/
    ├── database.yaml
    ├── backend.yaml
    └── frontend.yaml
```
