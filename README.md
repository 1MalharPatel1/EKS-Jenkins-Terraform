# EKS-Jenkins-Terraform

## Overview

This project sets up a CI/CD pipeline using Jenkins on an Amazon EKS cluster, provisioned and managed with Terraform. It automates the deployment of infrastructure and application workloads.

## Prerequisites

- AWS CLI installed and configured
- Terraform installed
- kubectl installed
- Jenkins knowledge
- AWS IAM permissions for EKS and Terraform

## Folder Structure

```
EKS_Jenkins_Terraform/
├── modules/                # Terraform modules for reusable components
├── eks/                    # EKS cluster configuration
├── jenkins/                # Jenkins deployment manifests
├── terraform/              # Main Terraform configuration files
├── scripts/                # Helper scripts for automation
└── README.md               # Project documentation
```

## Setup Instructions

1. **Clone the Repository**
    ```bash
    git clone <repository-url>
    cd EKS_Jenkins_Terraform
    ```

2. **Provision Infrastructure**
    - Navigate to the `terraform/` directory.
    - Initialize Terraform:
      ```bash
      terraform init
      ```
    - Apply the configuration:
      ```bash
      terraform apply
      ```

3. **Deploy Jenkins**
    - Navigate to the `jenkins/` directory.
    - Apply the Kubernetes manifests:
      ```bash
      kubectl apply -f jenkins-deployment.yaml
      ```

4. **Access Jenkins**
    - Retrieve the Jenkins service URL:
      ```bash
      kubectl get svc -n jenkins
      ```
    - Open the URL in your browser and log in.

## Cleanup

To destroy the infrastructure:
```bash
terraform destroy
```