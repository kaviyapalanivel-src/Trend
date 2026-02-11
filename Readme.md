# DevOps CI/CD Pipeline with AWS EKS, Jenkins, Prometheus & Grafana

This project demonstrates a complete DevOps CI/CD workflow for deploying a containerized application on AWS EKS with automated build, deployment, and monitoring.

The implementation follows industry-standard DevOps practices with a strong focus on automation, scalability, Infrastructure as Code, and observability.

---

## Project Objectives

- Automate application build and deployment using CI/CD
- Deploy containerized applications on Kubernetes (AWS EKS)
- Implement monitoring using Prometheus and Grafana
- Apply Infrastructure as Code principles using Terraform
- Follow a production-oriented DevOps workflow

---

## Tools & Technologies Used

- GitHub – Source code management  
- Jenkins – CI/CD automation  
- Docker – Application containerization  
- DockerHub – Container image registry  
- AWS EKS – Kubernetes orchestration  
- Terraform – Infrastructure as Code  
- Helm – Kubernetes package management  
- Prometheus – Metrics collection  
- Grafana – Metrics visualization  

---

## Architecture

The architecture follows a cloud-native CI/CD approach:

- Jenkins runs on an EC2 instance
- Application is containerized using Docker
- Docker images are stored in DockerHub
- Kubernetes workloads run on AWS EKS
- Application is exposed using AWS Load Balancer
- Monitoring is handled using Prometheus and Grafana

<img width="1536" height="1024" alt="archdiagram_landscape" src="https://github.com/user-attachments/assets/02932a90-da36-4a68-a76e-8663ed7c52a6" />

---

## CI/CD Workflow

1. Developer pushes code to GitHub  
2. Jenkins pipeline is triggered automatically  
3. Docker image is built from source code  
4. Image is pushed to DockerHub  
5. Kubernetes deployment is updated in AWS EKS  
6. Application is exposed using AWS Load Balancer  
7. Metrics are collected and visualized using Grafana  

---

## Project Structure

.
├── Jenkins/
│ └── Jenkinsfile
├── deployment.yaml
├── service.yaml
├── grafana-lb.yaml
├── main.tf
├── README.md
└── .gitignore


---

## Implementation Steps

### 1. Infrastructure Provisioning (Terraform)

Terraform is used to provision AWS infrastructure components including:

- VPC
- Subnets
- Security Groups
- EC2 instance for Jenkins

Commands used:

terraform init
terraform plan
terraform apply


---

### 2. Jenkins Setup

- Jenkins is installed on an EC2 instance
- Required plugins installed:
  - Docker
  - Kubernetes
  - Git
  - Pipeline

The Jenkins pipeline automates:
- Application build
- Docker image creation
- Image push to DockerHub
- Deployment to Kubernetes (EKS)

---

### 3. Docker Image Build & Push

The application is containerized and pushed to DockerHub:

docker build -t <dockerhub-username>/app-name .
docker push <dockerhub-username>/app-name


---

### 4. Kubernetes Deployment (AWS EKS)

The application is deployed to AWS EKS using Kubernetes manifests:

kubectl apply -f deployment.yaml
kubectl apply -f service.yaml


The service is exposed externally using a LoadBalancer.

---

### 5. Monitoring Setup (Prometheus & Grafana)

The monitoring stack is deployed using Helm:

helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

helm repo add grafana https://grafana.github.io/helm-charts

helm repo update

helm install prometheus prometheus-community/prometheus -n monitoring
helm install grafana grafana/grafana -n monitoring


Grafana is exposed externally using a LoadBalancer service.

---

## What Is Monitored

- Kubernetes cluster health
- Pod CPU usage
- Pod memory usage
- Node resource utilization
- Application availability

Grafana dashboards provide real-time visibility into cluster and application performance.

---

## Best Practices Followed

- Infrastructure as Code using Terraform
- Immutable Docker images
- Automated CI/CD pipeline using Jenkins
- Kubernetes-native deployment strategy
- Centralized monitoring and observability
- Clean Git version control using .gitignore

---

## Key Highlights

- End-to-end DevOps automation
- Production-style Kubernetes deployment
- Cloud-native monitoring with Prometheus and Grafana
- Scalable and extensible architecture
- Resume and interview-ready DevOps project

---

## Conclusion

This project demonstrates how modern DevOps tools integrate to deliver a reliable, automated, and observable cloud-native application using AWS, Kubernetes, and CI/CD best practices.
