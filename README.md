# Terraform AWS Template

## Overview
This Terraform template provides a well-structured framework for deploying AWS infrastructure using best practices.This is a reusable Terraform template for deploying resources on AWS. It follows best practices for modularity, scalability, and reusability.

## Directory Structure
- **environments/**: Separate configurations for `Development`, `Staging`, and `Production`.
- **modules/**: Reusable modules for VPC and EC2 instances.
- **scripts/**: Automation scripts for Terraform initialization and teardown.
- **Core Terraform Files**:
  - `provider.tf`: Defines cloud provider configuration.
  - `backend.tf`: Defines state management settings.
 
## Features
- Environment Isolation: Separate configurations for dev, staging, and production environments.
- Reusable Modules: Predefined modules for VPC, EC2, and RDS.
- Automation Scripts: Scripts to initialize and tear down infrastructure.
- Secure State Management: Remote backend configuration for Terraform state.

# Prerequisites
- Terraform Installed: Ensure Terraform is installed on your machine. Download it from here(https://www.terraform.io/downloads.html).
- AWS CLI Configured: Configure your AWS CLI with the necessary credentials using aws configure.
- Git: Clone this repository to your local machine.
# Getting Started
  # 1. Clone the Repository
  - git clone https://github.com/your-repo/terraform-aws-template.git
  - cd terraform-aws-template
  # 2. Configure the Backend
    Edit the backend.tf file to configure your remote backend (e.g., AWS S3 or Terraform Cloud).
    Example for AWS S3:
    terraform {
        backend "s3" {
          bucket = "your-terraform-state-bucket"
          key    = "path/to/your/state/file"
          region = "us-east-1"
        }
      }

# 3. Configure Environment Variables
    Navigate to the desired environment folder (e.g., environments/dev) and update the terraform.tfvars file with your variable values.
    Example terraform.tfvars:
      aws_region = "us-east-1"
      instance_type = "t2.micro"
      vpc_cidr = "10.0.0.0/16"
# 4. Initialize Terraform
    Run the init.sh script to initialize Terraform and download the necessary providers.

# 5. Apply the Configuration
    Apply the Terraform configuration to deploy the resources.
    terraform apply
# 6. Destroy Infrastructure (Optional)
    To tear down the infrastructure, run the teardown.sh script.
    ./scripts/teardown.sh

    
## How to Use
### 1. Initialize Terraform
```sh
sh scripts/init.sh
```
### 2. Apply Infrastructure
Navigate to the desired environment and apply:
```sh
cd environments/development
terraform apply
```
### 3. Destroy Infrastructure
```sh
sh scripts/teardown.sh
```

## Why Use This Template?
✅ **Modular & Scalable** - Separate environments prevent accidental changes.  
✅ **Reusable Modules** - Standardized components for VPC and EC2.  
✅ **Automation** - Scripts simplify Terraform operations.  
✅ **State Management** - Backend configuration ensures collaboration.  

---

This template helps in setting up a structured Terraform workflow, making AWS resource management efficient!


