# CI/CD Pipeline for Node.js Application Deployment to AWS ECS

This repository contains Terraform scripts and GitHub Actions configuration for setting up a CI/CD pipeline to deploy a Node.js application to AWS ECS (Elastic Container Service) using Fargate.

## Final Deployed URL
http://18.209.175.87:3000/


## Overview

The CI/CD pipeline automates the process of building, testing, and deploying a Node.js application to AWS ECS. Here's a brief overview of what's included:

- **Terraform Configuration**: The `main.tf` file contains the Terraform configuration to set up the necessary AWS infrastructure, including VPC, subnets, security groups, IAM roles, ECR repository, ECS cluster, task definition, and service.

- **GitHub Actions Workflow**: The `deploy.yml` file defines the GitHub Actions workflow. It triggers on every push to the `main` branch and performs the following steps:
  1. Checks out the code.
  2. Sets up Docker Buildx.
  3. Logs in to Amazon ECR.
  4. Builds, tags, and pushes the Docker image to ECR.
  5. Deploys the new image to ECS by updating the ECS service with the new task definition.

## Process Flow

1. **Terraform Configuration (`main.tf`)**:
   - Sets up AWS infrastructure including VPC, subnets, security groups, IAM roles, ECR repository, ECS cluster, task definition, and service.

2. **GitHub Actions Workflow (`deploy.yml`)**:
   - Triggers on every push to the `main` branch.
   - Checks out the code, sets up Docker Buildx, logs in to Amazon ECR, builds, tags, and pushes the Docker image to ECR.
   - Deploys the new image to ECS by updating the ECS service with the new task definition.

Please refer to the images in the `Images/` folder for visual guidance on the setup and deployment process.
