# Full-Stack App Deployment with Kubernetes and Minikube

For the detailed article, refer to:  
👉 [https://www.swtestacademy.com/deploy-full-stack-application-in-kubernetes/](https://www.swtestacademy.com/deploy-full-stack-application-in-kubernetes/)

---

## Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/safaa-40/fullstack-k8s-minikube.git
cd fullstack-k8s-minikube
```
### 2. Build and Deploy the Database
Go into the database folder, build the PostgreSQL image, and deploy it first.
```
cd database
docker build -t fullstackappdb .
cd ../k8s
kubectl apply -f database.yaml
```
### 3. Build and Deploy the Backend
Next, create the Flask backend image and deploy it.
```
cd ../backend
docker build -t backend .
cd ../k8s
kubectl apply -f backend.yaml
```
### 4. Build and Deploy the Frontend

Finally, build the React frontend image and deploy it.
```
cd ../frontend
docker build -t frontend .
cd ../k8s
kubectl apply -f frontend.yaml
```
### 5. Access the Application

Once all pods are running, open the frontend service using Minikube:
```
minikube service react-service
```

This command will open the application in your default browser.

### 6. Project Structure
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
