# DevOps AWS Infrastructure Project

## Overview
This project demonstrates a complete DevOps workflow using AWS, Terraform, Ansible, Docker, and Jenkins.

## Architecture
- AWS VPC with public and private subnets
- Bastion host for secure SSH access
- Jenkins server in private subnet
- Application server in private subnet
- Application Load Balancer (ALB) for traffic routing

## Tools Used
- AWS (EC2, VPC, ALB, IAM)
- Terraform (Infrastructure as Code)
- Ansible (Configuration Management)
- Docker (Containerization)
- Jenkins (CI/CD)

## Workflow
1. Infrastructure provisioned using Terraform
2. Ansible used to install Docker on servers
3. Jenkins used to automate build and deployment
4. Application containerized using Docker

## Ansible Setup
- Inventory configured for Jenkins and App servers
- Playbook used to install and start Docker service

## Note
AWS resources were terminated after project completion to avoid cost. The setup can be recreated using the provided configuration.
