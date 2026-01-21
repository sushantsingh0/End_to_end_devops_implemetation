End-to-End AWS EKS Infrastructure using Terraform
📌 Project Overview

This repository contains an end-to-end Terraform implementation to provision a fully automated AWS infrastructure for running Kubernetes workloads on Amazon EKS. The project follows Infrastructure as Code (IaC) and modular Terraform design, enabling reusable, scalable, and maintainable infrastructure.

The setup provisions a custom VPC, networking components, and an EKS cluster, making it suitable for real-world microservices and DevOps deployments.

🏗 Repository Structure
terraform-eks/
│
├── backend/
│   └── backend.tf
│
├── modules/
│   ├── vpc/
│   │   ├── main.tf
│   │   ├── variables.tf
│   │   └── outputs.tf
│   │
│   └── eks/
│       ├── main.tf
│       ├── variables.tf
│       └── outputs.tf
│
├── main.tf
├── variables.tf
└── outputs.tf

⚙️ Components Description
Backend

Configures remote Terraform state

Ensures state locking and consistency

Enables safe collaboration for team environments

VPC Module

Located under modules/vpc, this module is responsible for:

Creating a custom VPC

Public and private subnets across multiple AZs

Internet Gateway and route tables

Networking foundation for EKS

EKS Module

Located under modules/eks, this module handles:

EKS cluster creation

Managed node groups

IAM roles and policies for cluster and nodes

Secure and scalable Kubernetes control plane

Root Configuration

main.tf: Orchestrates module usage and dependency wiring

variables.tf: Centralized input variables (region, cluster name, CIDR ranges, node size, etc.)

outputs.tf: Exposes important outputs such as VPC ID, subnet IDs, and EKS cluster details

🚀 How to Deploy
1️⃣ Initialize Terraform
terraform init

2️⃣ Validate and Review Plan
terraform plan

3️⃣ Apply Infrastructure
terraform apply

4️⃣ Configure Kubernetes Access
aws eks update-kubeconfig --region <region> --name <cluster-name>

🔐 Best Practices Implemented

Modular Terraform architecture

Remote state management

Clear separation of networking and compute

Reusable and environment-ready code

AWS-recommended EKS setup

🧰 Technologies Used

Terraform

AWS EKS

AWS VPC

IAM

Kubernetes

📈 Use Cases

Kubernetes-based microservices deployment

DevOps / SRE portfolio project

Learning Terraform modules and AWS EKS

Production-ready infrastructure automation

📄 Prerequisites

Terraform >= 1.x

AWS CLI configured

kubectl installed

Valid AWS credentials
