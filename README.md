# 🚀 AWS Infrastructure Automation using Terraform

## 📌 Project Overview

This project demonstrates how to deploy a fully automated AWS infrastructure using **Terraform (Infrastructure as Code)**. It includes networking, container deployment, and load balancing.

---

## 🛠️ Tools & Technologies Used

* Terraform
* AWS (VPC, ECS, ALB)
* Docker (NGINX container)
* Git & GitHub

---

## 🧱 Architecture Components

* VPC (Virtual Private Cloud)
* Public Subnets (Multi-AZ)
* Internet Gateway
* Route Tables
* Security Groups
* ECS Cluster (Fargate)
* Application Load Balancer (ALB)

---

## ⚙️ Step-by-Step Implementation

### 🔹 Step 1: Install Terraform

```bash
terraform -v
```

---

### 🔹 Step 2: Create Project Directory

```bash
mkdir terraform-project
cd terraform-project
```

---

### 🔹 Step 3: Create Terraform Files

```bash
New-Item main.tf
New-Item provider.tf
New-Item variables.tf
New-Item outputs.tf
New-Item terraform.tfvars
```

---

### 🔹 Step 4: Configure AWS Provider

```hcl
provider "aws" {
  region = "ap-south-1"
}
```

---

### 🔹 Step 5: Initialize Terraform

```bash
terraform init
```

---

### 🔹 Step 6: Create VPC

```hcl
resource "aws_vpc" "main" {
  cidr_block = "10.0.0.0/16"
}
```

---

### 🔹 Step 7: Create Subnets (Multi-AZ)

```hcl
resource "aws_subnet" "public" { ... }
resource "aws_subnet" "public2" { ... }
```

---

### 🔹 Step 8: Add Internet Gateway & Routing

```hcl
resource "aws_internet_gateway" "gw" { ... }
resource "aws_route_table" "rt" { ... }
```

---

### 🔹 Step 9: Security Group

```hcl
resource "aws_security_group" "web_sg" { ... }
```

---

### 🔹 Step 10: ECS Cluster & Task

```hcl
resource "aws_ecs_cluster" "main" { ... }
resource "aws_ecs_task_definition" "app" { ... }
```

---

### 🔹 Step 11: Application Load Balancer

```hcl
resource "aws_lb" "app_lb" { ... }
resource "aws_lb_target_group" "tg" { ... }
resource "aws_lb_listener" "listener" { ... }
```

---

### 🔹 Step 12: ECS Service with Load Balancer

```hcl
resource "aws_ecs_service" "app" { ... }
```

---

### 🔹 Step 13: Deploy Infrastructure

```bash
terraform plan
terraform apply
```

---

## 🌐 Output

* Application deployed on ECS (Fargate)
* Accessible via ALB DNS
* Displays NGINX Welcome Page

---

## 🔐 Security Note

AWS credentials were **not uploaded to GitHub** and handled securely.

---

## 🎯 Key Learnings

* Infrastructure as Code (IaC)
* AWS networking concepts
* ECS container deployment
* Load balancing
* GitHub version control

---

## ✅ Conclusion

This project successfully demonstrates automated cloud infrastructure deployment using Terraform with high availability and scalability.
