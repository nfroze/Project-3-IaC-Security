# Project 3: IaC Security

## Overview

AWS infrastructure provisioning with Terraform. IAM policies configured with least privilege. CI/CD pipeline integrates Checkov for infrastructure scanning before deployment.

## Technologies

- Terraform - Infrastructure as Code for AWS resources
- AWS - IAM, CloudTrail, GuardDuty configuration
- Checkov - IaC security scanning
- GitHub Actions - CI/CD automation

## Implementation

### Security Features
- Least privilege IAM policies for admin, developer, and DevSecOps roles
- Automated IaC scanning with Checkov
- Terraform state management via S3 backend
- Separate scan and deploy stages

### CI/CD Workflow
1. Code checkout and AWS credential configuration
2. Terraform initialisation
3. Checkov security scan
4. Terraform plan generation
5. Infrastructure deployment (only if scan passes)

## Project Structure

```
Project-3-IaC-Security/
├── terraform/
│   ├── main.tf          # AWS resource definitions
│   ├── variables.tf     # Configuration variables
│   └── backend.tf       # S3 state backend
├── .github/
│   └── workflows/
│       └── terraform.yml # CI/CD pipeline
└── policies/
    └── iam-policies.json # IAM policy definitions
```

## AWS Resources Configured

- IAM roles and policies
- S3 buckets with encryption
- CloudTrail logging
- GuardDuty threat detection
- VPC and security groups

## Pipeline Features

- Two-stage pipeline: scan then deploy
- Checkov misconfiguration detection
- Terraform plan review before apply
- Deployment blocked if security issues found