# Infrastructure

This repository contains all the infrastructure code required to deploy and manage the e-commerce platform, including Terraform scripts, Kubernetes manifests, and cloud configuration.

## Table of Contents

- [Overview](#Overview)
- [Technology Stack](#technology-stack)
- [Prerequisites](#prerequisites)
- [DirectoryStructure](#DirectoryStructure)
- [Installation](#Installation)
- [Infrastructure Deployment](#InfrastructureDeployment)
- [Testing](#testing)


## Overview

This repository uses Infrastructure as Code (IaC) principles to provision, deploy, and manage the entire e-commerce platform. It includes:

* Cloud resources provisioning with Terraform
* Microservices deployment on Kubernetes
* Configurations for Docker-based services
* CI/CD pipeline integration for automated deployment

## Technology Stack

- **IaC:** Terraform
- **Container Orchestration:** Kubernetes
- **Containerization:** Docker
- **Cloud:** AWS
- **CI/CD Tools:** Github Actions

## Prerequisites

Before you begin, ensure you have met the following requirements:

* Terraform v1.0 or higher
* kubectl command-line tool
* Docker installed and running
* AWS CLI
* AWS IAM credential

## Directory Structure

The repository is structured as follows:
```sql
infrastructure/
├── terraform/
│   ├── main.tf
│   ├── variables.tf
│   ├── outputs.tf
│   └── modules/
├── kubernetes/
│   ├── deployments/
│   │   ├── user-service-deployment.yaml
│   │   ├── product-service-deployment.yaml
│   │   └── ...
│   ├── services/
│   │   ├── user-service.yaml
│   │   ├── product-service.yaml
│   │   └── ...
│   ├── ingress/
│   │   └── ingress.yaml
│   └── configmaps-secrets/
│       ├── configmap.yaml
│       └── secret.yaml
└── README.md
```

## Installation 
1. ***Navigate to the Terraform directory:***

```bash
cd terraform
```
2. ***Initialise Terraform:***

```bash
terraform init
```
3. ***Review the execution plan:***

```bash
terraform plan
```

4. ***Apply the Terraform scripts:***

```bash
terraform apply
```
This will provision the necessary cloud infrastructure, including the Kubernetes cluster, networking components, storage, and other cloud resources.
## Kubernetes Setup

1. Configure kubect1:
   Ensure your kubect1 context is set to the newly created Kubernetes cluster.

2.Deploy Services:
  Apply the Kubernetes manifests to deploy your services.

```bash
kubectl apply -f kubernetes/deployments/
kubectl apply -f kubernetes/services/
```

3.Apply ConfigMaps and Secrets
```bash
kubectl apply -f kubernetes/configmaps-secrets/
```

4. Set up Ingress:
   If you are using ingress for routing traffic to your services:
```bash
kubectl apply -f kubernetes/ingress/ingress.yaml
```

## Infrastructure Deployment

Once the infrastructure is deployed, you can view the resources in the AWS Console. Additionally, you can use Terraform to manage and update your infrastructure as needed.

## Testing

### Terraform Testing
You can validate your Terraform code using terraform validate to ensure there are no syntax or configuration errors:

```bash
terraform validate
```
You can also run terraform plan to simulate changes without applying them.

### Kubernetes Testing
After deploying services to Kubernetes, you can check the status of the pods and services:

```bash
kubectl get pods
kubectl get services
```
Ensure that all pods are running and services are accessible.
