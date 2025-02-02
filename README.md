# Terraform AWS Infrastructure for Highly Available Web Servers

This Terraform configuration provisions a highly available web server infrastructure on AWS, featuring an Application Load Balancer (ALB), Auto Scaling Group, and multi-AZ deployment.

## Architecture Overview
![Architecture Diagram](https://github.com/Amr-Awad/AutoScallerTerraform/blob/main/architecture.jfif)

- **VPC** with public and private subnets across 2 Availability Zones (AZs).
- **NAT Gateways** for outbound internet access from private subnets.
- **Application Load Balancer (ALB)** distributing traffic to EC2 instances.
- **Auto Scaling Group** with launch template for automatic scaling.
- **CloudWatch Alarms** to trigger scaling based on CPU usage.

## Features
- 🛡️ Security groups restricting traffic to HTTP/SSH only.
- 🔄 Auto Scaling maintains 2-4 EC2 instances across private subnets.
- 🌐 Public-facing ALB with health checks.
- 🔑 SSH key pair auto-generated for EC2 access.

## Prerequisites
1. **AWS Account**: Configured with CLI credentials (`aws configure`).
2. **Terraform**: [Installed](https://www.terraform.io/downloads.html) (v1.0+ recommended).
3. **Key Pair**: Terraform will generate an `ec2.pem` file automatically.
