# Terraform AWS Template

## Overview
This Terraform template provides a well-structured framework for deploying AWS infrastructure using best practices.

## Directory Structure
- **environments/**: Separate configurations for `Development`, `Staging`, and `Production`.
- **modules/**: Reusable modules for VPC and EC2 instances.
- **scripts/**: Automation scripts for Terraform initialization and teardown.
- **Core Terraform Files**:
  - `provider.tf`: Defines cloud provider configuration.
  - `backend.tf`: Defines state management settings.

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
