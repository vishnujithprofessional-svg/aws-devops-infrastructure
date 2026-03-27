DevOps AWS Infrastructure Project

Overview  
This project demonstrates an end-to-end DevOps workflow using AWS, Terraform, Ansible, Docker, and Jenkins. It includes infrastructure provisioning, configuration management, CI/CD automation, and containerized application deployment.

---

Architecture  
- AWS VPC with public and private subnets  
- Bastion host for secure SSH access  
- Jenkins server in private subnet  
- Application server in private subnet  
- Application Load Balancer (ALB) for external traffic routing  

---

Load Balancer (ALB)  
An Application Load Balancer (ALB) is used to expose services to users while keeping backend servers secure.

- Deployed in public subnets  
- Routes incoming HTTP requests to private servers  
- Performs health checks to ensure availability  
- Path-based routing used for accessing Jenkins (/jenkins)  

This ensures that private instances are never directly exposed to the internet.

---

Tools Used  
- AWS (EC2, VPC, ALB, IAM)  
- Terraform (Infrastructure as Code)  
- Ansible (Configuration Management)  
- Docker (Containerization)  
- Jenkins (CI/CD)  

---

Workflow  
1. Infrastructure is provisioned using Terraform (VPC, subnets, EC2)  
2. Ansible installs Docker on Jenkins and application servers  
3. Jenkins automates build and deployment process  
4. Application is containerized using Docker  
5. ALB routes user traffic to application server  

---

Ansible Setup  
- Inventory configured for Jenkins and App servers  
- Playbook used to install and start Docker service  

---

Result  
- Application successfully deployed and accessible through ALB  
- Jenkins automation configured and operational  
- Secure architecture with private subnets and bastion access  

---

Note  
AWS resources were terminated after project completion to avoid cost. The setup can be recreated using the provided configuration.
