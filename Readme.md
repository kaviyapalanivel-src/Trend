DevOps CI/CD Pipeline with AWS EKS, Jenkins, Prometheus & Grafana

This project demonstrates a complete DevOps CI/CD workflow for deploying a containerized application on AWS EKS with automated build, deployment, and monitoring.

The implementation follows industry-standard DevOps practices, focusing on automation, scalability, and observability.

📌 Project Objectives

Automate application build and deployment using CI/CD

Deploy containerized applications on Kubernetes (EKS)

Implement monitoring using Prometheus and Grafana

Use Infrastructure as Code principles

Follow production-oriented DevOps workflow

🛠️ Tools & Technologies Used

GitHub – Source code management

Jenkins – CI/CD automation

Docker – Application containerization

DockerHub – Image registry

AWS EKS – Kubernetes orchestration

Terraform – Infrastructure as Code

Helm – Kubernetes package management

Prometheus – Metrics collection

Grafana – Metrics visualization

🏗️ Architecture

(Architecture diagram added here)

⚙️ CI/CD Workflow

Developer pushes code to GitHub

Jenkins pipeline is triggered automatically

Docker image is built from source code

Image is pushed to DockerHub

Kubernetes deployment is updated in EKS

Application is exposed via AWS Load Balancer

Monitoring data is collected and visualized

📂 Project Structure
.
├── Jenkins/
│   └── Jenkinsfile
├── deployment.yaml
├── service.yaml
├── grafana-lb.yaml
├── main.tf
├── README.md
└── .gitignore

🚀 Implementation Steps
1️⃣ Infrastructure Provisioning (Terraform)

Terraform is used to provision AWS resources such as:

VPC

Subnet

Security Groups

EC2 instance for Jenkins

terraform init
terraform plan
terraform apply

2️⃣ Jenkins Setup

Jenkins is installed on an EC2 instance

Required plugins:

Docker

Kubernetes

Git

Jenkins pipeline automates:

Build

Docker image creation

Image push to DockerHub

Kubernetes deployment

3️⃣ Docker Image Build & Push
docker build -t <dockerhub-username>/app-name .
docker push <dockerhub-username>/app-name

4️⃣ Kubernetes Deployment (EKS)

Application is deployed to AWS EKS using Kubernetes manifests:

kubectl apply -f deployment.yaml
kubectl apply -f service.yaml


Service is exposed externally using LoadBalancer.

5️⃣ Monitoring Setup (Prometheus & Grafana)

Monitoring stack is deployed using Helm:

helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo add grafana https://grafana.github.io/helm-charts
helm repo update

helm install prometheus prometheus-community/prometheus -n monitoring
helm install grafana grafana/grafana -n monitoring


Grafana is exposed using LoadBalancer for external access.

📊 What Is Monitored

Kubernetes cluster health

Pod CPU usage

Pod memory usage

Node resource utilization

Application availability

Dashboards provide real-time visibility into cluster performance.

🔐 Best Practices Followed

Infrastructure as Code using Terraform

Immutable Docker images

Automated CI/CD pipeline

Kubernetes-native deployment

Centralized monitoring and observability

Clean Git version control with .gitignore

⭐ Key Highlights

End-to-end DevOps automation

Production-style Kubernetes deployment

Cloud-native monitoring setup

Scalable and extensible architecture

Resume and interview ready project

📌 Conclusion

This project demonstrates how modern DevOps tools work together to deliver a reliable, automated, and observable cloud application using AWS and Kubernetes.
