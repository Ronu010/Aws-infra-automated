﻿# AWS Infrastructure Automated Deployment

## Project Overview

This project automates the deployment of AWS infrastructure using Terraform. The goal is to enable a scalable, secure, and cost-effective infrastructure for web applications. It integrates with Jenkins for continuous integration and deployment (CI/CD) and uses CloudWatch for real-time monitoring.

## Technologies Used

- **Terraform**: Infrastructure as Code (IaC) to automate the provisioning of AWS resources.
- **AWS**: The infrastructure is deployed on Amazon Web Services, including EC2, VPC, CloudWatch, and S3.
- **Jenkins**: Used for automating the CI/CD pipeline.
- **GitHub**: Version control and code repository.
- **AWS CloudWatch**: Real-time monitoring and alerting for infrastructure health.
- **AWS Trusted Advisor**: Optimization of costs and security for AWS resources.

## Project Structure

```plaintext
aws-infra/
├── .terraform/                  # Terraform configuration and state
├── main.tf                      # Main Terraform configuration file
├── variables.tf                 # Terraform variables
├── outputs.tf                   # Terraform outputs
├── README.md                    # Project documentation
├── scripts/                     # Automation scripts (if any)
├── .gitignore                   # Git ignore file for Terraform files and others
└── jenkins/                     # Jenkins pipeline configuration files (if any)

Setup Instructions-------------------
Prerequisites
Terraform installed on your local machine.
AWS credentials set up (AWS Access Key and Secret Key).
Jenkins installed for the CI/CD pipeline.
GitHub repository for version control.

#--------------------------------------- Steps to Deploy -----------------------------------------------------------#

Clone the repository:

1.git clone https://github.com/Ronu010/Aws-infra-automated.git
  cd aws-infra

2.Initialize Terraform:
  terraform init

3.Apply the Terraform configurations to deploy the infrastructure:
  terraform apply

4.Monitor the deployed infrastructure using AWS CloudWatch.

*CI/CD Pipeline
The CI/CD pipeline is managed using Jenkins. It is triggered every time changes are pushed to the GitHub repository, and it ensures automatic deployment of infrastructure updates using Terraform.

*Monitoring and Optimization
CloudWatch: Monitors vital metrics like CPU usage, memory usage, and network traffic.
AWS Trusted Advisor: Helps to optimize the deployed infrastructure for security and cost-efficiency.

***Troubleshooting****
If you encounter issues related to Terraform state or deployment, ensure that the .terraform/ directory is excluded from Git tracking by adding it to .gitignore.
For large files, use Git LFS (Large File Storage) to manage and store them efficiently.

Difficulties faced during project----Terraform State Management – Terraform tracks resources in a state file, and if it's not managed properly, it can cause conflicts. To avoid this, I would use remote state storage like AWS S3 with DynamoDB for state locking.

HOW TO OVERCOME THIS ----
Use remote backend storage like AWS S3 to store Terraform state securely.
Enable state locking with DynamoDB to prevent multiple users from modifying the state file simultaneously.
Regularly back up the state file to avoid accidental deletion or corruption.


THANKS FOR READING.................................................................................

