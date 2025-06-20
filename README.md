 DevOps Coding Assessment project.

---



---

### ✅ **📄 Sample `README.md`**

````markdown
# DevOps Coding Assessment – Ruby on Rails with PostgreSQL

This project demonstrates a complete CI/CD pipeline for deploying a simple Ruby on Rails application using Docker, Kubernetes, ArgoCD, and Tekton.

---

## 🔧 Step 1 – Docker

- Built a `Dockerfile` for a Rails app.
- PostgreSQL and Rails app run in separate containers via `docker-compose`.

```bash
cd docker/
docker-compose up --build
````

---

## ☸️ Step 2 – Kubernetes

* Rails app deployed using `Deployment`.
* PostgreSQL deployed using `StatefulSet`.
* Ingress configured using NGINX Ingress Controller.

### Run on Minikube:

```bash
kubectl apply -f kubernetes/
```

---

## 🚀 Step 3 – ArgoCD GitOps

* ArgoCD used to sync Kubernetes manifests from a private GitHub repo.
* Includes `application.yaml`, config maps, and repo credentials.

### Install ArgoCD:

```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

---

## 🔁 Step 4 – Tekton CI/CD

* Created Tekton pipeline that:

  1. Clones the app from GitHub
  2. Builds image using Kaniko
  3. Pushes image to Docker Hub

### Run from Dashboard:

```bash
kubectl apply -f tekton/
```

---

## 📦 Folder Structure

```
docker/       → Dockerfile and docker-compose
kubernetes/   → All K8s manifests (Deployment, StatefulSet, Ingress)
argocd/       → ArgoCD application and config files
tekton/       → CI pipeline files using Tekton
app/          → Ruby on Rails application (optional)
```

---



---

## 🔐 Credentials (for demo only)

* PostgreSQL User: `postgres`
* PostgreSQL Password: `password`

---
```

## 🔗 Useful Links

* [ArgoCD Docs](https://argo-cd.readthedocs.io/en/stable/)
* [Tekton Docs](https://tekton.dev/docs/)
* [NGINX Ingress](https://kubernetes.github.io/ingress-nginx/deploy/)

---

