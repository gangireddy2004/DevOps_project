# 🚀 Cloud DevOps Project

## 📌 Project Overview

This project demonstrates a complete end-to-end DevOps workflow using:

* HTML
* CSS
* JavaScript
* Docker
* Kubernetes
* Jenkins
* Helm
* Prometheus
* Grafana

A static web application is containerized using Docker, deployed into Kubernetes, automated through Jenkins CI/CD, and monitored using Prometheus and Grafana. fileciteturn0file0

---

# 🏗️ Architecture

```text
Developer
   ↓
GitHub Repository
   ↓
Jenkins CI/CD Pipeline
   ↓
Docker Image Build
   ↓
Kubernetes Deployment
   ↓
Prometheus Monitoring
   ↓
Grafana Dashboard
```

---

# 📂 Project Structure

```text
StaticWeb/
│
├── index.html
├── style.css
├── script.js
├── Dockerfile
│
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
│
├── Jenkinsfile
└── README.md
```

---

# ⚙️ Technologies Used

| Tool       | Purpose                       |
| ---------- | ----------------------------- |
| Docker     | Containerization              |
| Kubernetes | Container Orchestration       |
| Jenkins    | CI/CD Automation              |
| GitHub     | Source Code Management        |
| Helm       | Kubernetes Package Management |
| Prometheus | Monitoring                    |
| Grafana    | Visualization Dashboard       |

---

# ▶️ Run Project Locally

## 1. Build Docker Image

```bash
docker build -t my-website .
```

## 2. Run Docker Container

```bash
docker run -d -p 8081:80 my-website
```

Open in browser:

```text
http://localhost:8081
```

---

# ☸️ Kubernetes Deployment

Deploy application:

```bash
kubectl apply -f k8s/
```

Verify resources:

```bash
kubectl get pods
kubectl get svc
kubectl get deployments
```

Scale deployment:

```bash
kubectl scale deployment my-website --replicas=3
```

Self-healing test:

```bash
kubectl delete pod POD_NAME
```

Kubernetes automatically recreates the deleted pod.

---

# 🔄 Jenkins CI/CD Pipeline

Jenkins automates:

* GitHub code pull
* Docker image build
* Kubernetes deployment

## Jenkins Pipeline

```groovy
pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/gangireddy2004/DevOps_project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t my-website .'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f k8s/'
            }
        }
    }
}
```

---

# 📊 Monitoring Stack

## Install Helm

```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
```

## Install Prometheus & Grafana

```bash
helm install monitoring prometheus-community/kube-prometheus-stack
```

Access Grafana:

```bash
kubectl port-forward svc/monitoring-grafana 3000:80
```

Open:

```text
http://localhost:3000
```

Default Login:

| Username | Password      |
| -------- | ------------- |
| admin    | prom-operator |

---

# 📈 Key Features

* Docker Containerization
* Kubernetes Orchestration
* Jenkins CI/CD Automation
* Helm Package Management
* Prometheus Monitoring
* Grafana Dashboards
* Horizontal Scaling
* Kubernetes Self-Healing
* NodePort Networking

---

# ✅ Final Output

* Static website deployed successfully
* Docker container running
* Kubernetes pods running
* Jenkins pipeline automated
* Monitoring integrated successfully
* Scaling and self-healing verified

---

# 🐳 Complete Docker Commands

## Check Docker Version

```bash
docker --version
```

## Pull Docker Image

```bash
docker pull nginx
```

## Build Docker Image

```bash
docker build -t my-website .
```

## Run Docker Container

```bash
docker run -d -p 8081:80 my-website
```

## Check Running Containers

```bash
docker ps
```

## Check All Containers

```bash
docker ps -a
```

## Stop Container

```bash
docker stop CONTAINER_ID
```

## Start Container

```bash
docker start CONTAINER_ID
```

## Restart Container

```bash
docker restart CONTAINER_ID
```

## Remove Container

```bash
docker rm CONTAINER_ID
```

## Remove Docker Image

```bash
docker rmi IMAGE_ID
```

## View Container Logs

```bash
docker logs CONTAINER_ID
```

## Open Container Terminal

```bash
docker exec -it CONTAINER_ID bash
```

## Docker Login

```bash
docker login
```

## Tag Docker Image

```bash
docker tag my-website username/my-website:v1
```

## Push Docker Image

```bash
docker push username/my-website:v1
```

---

# ☸️ Complete Kubernetes Commands

## Check Kubernetes Cluster

```bash
kubectl cluster-info
```

## Check Nodes

```bash
kubectl get nodes
```

## Deploy Kubernetes Resources

```bash
kubectl apply -f k8s/
```

## Get Pods

```bash
kubectl get pods
```

## Watch Pods Live

```bash
kubectl get pods -w
```

## Get Services

```bash
kubectl get svc
```

## Get Deployments

```bash
kubectl get deployments
```

## Describe Pod

```bash
kubectl describe pod POD_NAME
```

## View Pod Logs

```bash
kubectl logs POD_NAME
```

## Delete Pod

```bash
kubectl delete pod POD_NAME
```

## Scale Deployment

```bash
kubectl scale deployment my-website --replicas=3
```

## Restart Deployment

```bash
kubectl rollout restart deployment my-website
```

## Check Rollout Status

```bash
kubectl rollout status deployment my-website
```

## Delete Deployment

```bash
kubectl delete deployment my-website
```

## Delete Service

```bash
kubectl delete svc my-website-service
```

## Delete All Kubernetes Resources

```bash
kubectl delete -f k8s/
```

## Port Forward Service

```bash
kubectl port-forward svc/my-service 8080:80
```

## Check Namespaces

```bash
kubectl get namespaces
```

## Check Events

```bash
kubectl get events
```

---

# 🔄 Complete Jenkins Commands

## Start Jenkins

### Windows

```bash
net start jenkins
```

### Linux

```bash
sudo systemctl start jenkins
```

## Stop Jenkins

### Windows

```bash
net stop jenkins
```

### Linux

```bash
sudo systemctl stop jenkins
```

## Restart Jenkins

```bash
sudo systemctl restart jenkins
```

## Check Jenkins Status

```bash
sudo systemctl status jenkins
```

## Jenkins Initial Admin Password

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

## Open Jenkins

```text
http://localhost:8080
```

---

# 📄 Complete Jenkins Pipeline

```groovy
pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/gangireddy2004/DevOps_project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t my-website .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker run -d -p 8081:80 my-website'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f k8s/'
            }
        }

        stage('Check Kubernetes Pods') {
            steps {
                bat 'kubectl get pods'
            }
        }
    }
}
```

---

# 📦 Helm Commands

## Check Helm Version

```bash
helm version
```

## Add Helm Repository

```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
```

## Update Helm Repository

```bash
helm repo update
```

## Install Monitoring Stack

```bash
helm install monitoring prometheus-community/kube-prometheus-stack
```

## List Helm Releases

```bash
helm list
```

## Uninstall Helm Release

```bash
helm uninstall monitoring
```

---

# 📊 Grafana Access

## Port Forward Grafana

```bash
kubectl port-forward svc/monitoring-grafana 3000:80
```

Open in browser:

```text
http://localhost:3000
```

Default Login Credentials:

| Username | Password      |
| -------- | ------------- |
| admin    | prom-operator |

---

# ✅ Final Verification Commands

```bash
docker ps
```

```bash
kubectl get pods
```

```bash
kubectl get svc
```

```bash
kubectl get deployments
```

```bash
helm list
```

```bash
kubectl get nodes
```

---

# 👨‍💻 Author

**Gangireddy**
