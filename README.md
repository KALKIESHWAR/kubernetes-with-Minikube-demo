# 🚀 Kubernetes NGINX Deployment with Minikube

This project demonstrates how to create a local Kubernetes cluster using Minikube, deploy an NGINX web server, expose it via a NodePort service, and manage scaling and cleanup operations.

---

## 📁 Project Structure

```
.
├── deployment.yaml     # Defines the NGINX Deployment
├── service.yaml        # Exposes the deployment using NodePort
├── OUTPUTS/        # Screenshots of pod, service, deployment, and browser view
└── README.md           # Project instructions and documentation
```

---

## 🛠️ Tools & Technologies

- [Minikube](https://minikube.sigs.k8s.io/)
- [Kubernetes](https://kubernetes.io/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)
- [Docker](https://www.docker.com/)
- NGINX container

---

## 📦 Setup Instructions

### 1. Prerequisites
- Docker installed and running
- `kubectl` and `minikube` installed
- At least 2 CPUs, 2GB RAM, 20GB free disk space
- Internet connection

---

### 2. Start Kubernetes Cluster

```bash
minikube start --driver=docker
```

Verify the cluster:

```bash
kubectl cluster-info
minikube status
```

---

### 3. Deploy NGINX

Create and apply the deployment:

```bash
kubectl apply -f deployment.yaml
```

Check status:

```bash
kubectl get deployments
kubectl get pods
```

---

### 4. Expose the Deployment

```bash
kubectl apply -f service.yaml
kubectl get services
```

Open the service in your browser:

```bash
minikube service nginx-service
```

---

### 5. Scale the Deployment

Scale to 4 replicas:

```bash
kubectl scale deployment nginx-deployment --replicas=4
kubectl get pods
```

---

### 6. Cleanup (Optional)

```bash
kubectl delete -f service.yaml
kubectl delete -f deployment.yaml
minikube stop
```

---

## 🖼️ Screenshots

Make sure to include the following screenshots in your GitHub repo:
- `kubectl get pods`
- `kubectl get services`
- `kubectl get deployments`
- Web browser with NGINX running

Save them in a folder named `OUTPUTS/`.

---

kubectl set image deployment/<name> <container>=<new-image>
```

---

## ✅ Submission Checklist

- [x] `deployment.yaml` uploaded  
- [x] `service.yaml` uploaded  
- [x] Screenshots added in `screenshots/` folder  
- [x] `README.md`  
- [x] GitHub repository pushed and ready to submit

---

## 🎉 Thank You!

This project helped me practice real-world Kubernetes concepts using Minikube on my local system.
