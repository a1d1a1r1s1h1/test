# SimpleTimeService

A minimalist microservice that returns the current timestamp and the visitor's IP address.

## Features
- Returns JSON response with current UTC timestamp and IP address.
- Lightweight, containerized, and runs as a **non-root user**.
- Built with Python Flask.

## Prerequisites
- [Docker](https://docs.docker.com/get-docker/)
- [Git](https://git-scm.com/downloads)

## Installation & Usage

### 1️⃣ Clone the Repository
```
git clone https://github.com/a1d1a1r1s1h1/test

cd test/app
```
-------------------------------------------------------------------------------------------------------

# SimpleTimeService - AWS Deployment using Terraform

This contains terraform modules & scripts to deploy the SimpleTimeService microservice on AWS ECS Fargate using an Application Load Balancer (ALB). The infrastructure includes a VPC, public and private subnets, ECS cluster, and IAM roles.

terraform/
├── main.tf            # Main Terraform configuration
├── vpc.tf             # VPC, Subnets, Internet Gateway
├── ecs.tf             # ECS Cluster, Task Definition, and Service
├── alb.tf             # Application Load Balancer
├── iam.tf             # IAM Roles for ECS
├── variables.tf       # Input variables
├── outputs.tf         # Outputs
├── terraform.tfvars   # Default values for variables
├── README.md          # Deployment instructions


---

## **Pre-Requisites**

### **1️⃣ Install Required Tools**
Ensure the following tools are installed:
- [Terraform](https://www.terraform.io/downloads)
- [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html) (configured with an IAM user having admin permissions)

### **2️⃣ Configure AWS Credentials**
Ensure AWS credentials are set up on your system:

aws configure

Steps to deploy:

Clone and cd
```
git clone https://github.com/a1d1a1r1s1h1/test

cd test/terraform
```
Modify terraform.tfvars with appropriate values
```
terraform init

terraform plan -var-file=terraform.tfvars

terraform apply -var-file=terraform.tfvars -auto-approve

terraform output alb_url

curl http://alb-url
```
To destroy:
```
terraform destroy -var-file=terraform.tfvars -auto-approve
```