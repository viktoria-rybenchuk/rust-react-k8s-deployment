# React + Rust + Postgres Kubernetes Deployment

This repository contains **Kubernetes deployment manifests** for the [React + Rust + Postgres](https://github.com/docker/awesome-compose/tree/master/react-rust-postgres) application.

It does **not include the source code** of the frontend or backend. The manifests allow you to deploy the existing application stack on a Kubernetes cluster.

---

## Services

The deployment includes three main services:

1. **Frontend**
   - React application
   - Exposed via a LoadBalancer

2. **Backend**
   - Rust application
   - Connects to the Postgres database
   - Environment variables are configured for database access

3. **Database**
   - PostgreSQL
   - Uses a PersistentVolume for data persistence
   - Password and database configuration are set in environment variables

---

## Deployment

### Prerequisites

- Kubernetes cluster (minikube)
- `kubectl` configured
- Docker images for frontend and backend already built or available from a registry

### Steps

1. Create a namespace (optional):
```bash
kubectl create namespace react-rust-postgres
```
2. Change to the directory containing the manifests:
```bash
cd deployment
```
3. Deploy all resources:
```bash
kubectl apply -f .
```