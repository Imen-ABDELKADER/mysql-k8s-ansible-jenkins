# MySQL on Kubernetes – Fully Automated Deployment with Ansible & Jenkins

**DevOps **

End-to-end automation that provisions and deploys a production-ready MySQL database on a Kubernetes cluster using Infrastructure as Code (IaC) and CI/CD best practices.

## Project Overview

This project automates the deployment of MySQL on a Kubernetes cluster with the following components:

- Kubernetes cluster with NFS dynamic provisioning (persistent storage)
- Jenkins deployed as a pod using Ansible playbooks
- MySQL deployed via Helm chart (official Bitnami MySQL)
- Nexus Repository Manager as artifact/storage backend
- Full CI/CD pipeline ready for database schema migrations and backups

## Key Features

- 100% Infrastructure as Code (Ansible + Helm + Kubernetes manifests)
- Persistent storage using NFS + StorageClass
- Jenkins CI/CD server running inside the cluster
- Secure MySQL deployment with root/password secrets management
- Easy scaling and upgrades via Helm
- Ready for GitOps / ArgoCD integration

## Technologies Used

- Kubernetes (k8s)  
- Ansible  
- Jenkins  
- Helm  
- MySQL 8.x  
- NFS (persistent volumes)  
- Nexus Repository OSS  
- Linux (Ubuntu/CentOS)


## Quick Start

### 1. Prerequisites
- Kubernetes cluster (Minikube, Kind, or real cluster)
- Ansible installed on control node
- `kubectl` configured
- NFS server accessible (or use local-path for testing)

### 2. Deploy Everything


# From the project root
ansible-playbook -i inventory deploy/main.yml

# From the project root
ansible-playbook -i inventory deploy/main.yml
This single command will:

Deploy NFS provisioner (if needed)
Create StorageClass and Persistent Volumes
Deploy Jenkins via Ansible
Install Helm and deploy MySQL
Configure secrets and persistence

3. Access Services

Jenkins: http://<node-ip>:32000 (port-forward or NodePort)
MySQL root password:Bashkubectl get secret mysql -o jsonpath="{.data.mysql-root-password}" | base64 -d

Achievements

Fully automated database deployment on Kubernetes
Production-grade persistent storage with NFS
CI/CD integration with Jenkins running in-cluster
Reproducible and version-controlled infrastructure
Strong foundation for GitOps and automated database migrations

Future Improvements (Planned)

Add ArgoCD for GitOps
Implement automated backups to S3/MinIO
Add Prometheus + Grafana monitoring
Database migration pipeline with Flyway/Liquibase

Project actively maintained – feel free to star if you're into DevOps, Kubernetes, or IaC!
Perfect for DevOps Engineer, Cloud Engineer, or SRE portfolios.


