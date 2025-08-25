# Deploy & Manage ShopifyLite (Amazon-like Shopping Website) using DevOps Tools

**Terraform, Jenkins (CI/CD), SonarQube, Docker & Trivy on AWS Cloud**

## Scenario

ShopifyLite is a startup building an Amazon-clone eCommerce platform.

Developers focused on coding the shopping application (frontend + backend).

My role as a DevOps Engineer was to automate infrastructure provisioning and set up a robust CI/CD pipeline to ensure:

Fast deployments

Automated code quality & security scans

Reliable infrastructure on AWS

## Tech Stack

Infrastructure as Code (IaC): Terraform

CI/CD: Jenkins Pipeline (Jenkinsfile)

Code Quality: SonarQube

Security Scanning: Trivy & OWASP Dependency Check

Containerization: Docker

Cloud Provider: AWS (EC2, Security Groups, IAM, VPC)

## Project Workflow

Developers push code → GitHub repository (ShopifyLite app).

Jenkins pipeline (Jenkinsfile):

Pulls code from GitHub

Runs SonarQube scan

Runs Trivy scan on Docker image

Builds and pushes Docker image to DockerHub

Deploys app to EC2 (via Terraform-provisioned infra).

Users access the app → live on AWS (port 3000).

## Project Structure
terraform/       # Terraform configs for AWS infra
jenkins/         # Jenkins pipeline (CI/CD)
app/             # (Optional) ShopifyLite application source code
screenshots/     # Proof of deployment & results

## Terraform Setup (terraform/)

provider.tf → AWS provider config

main.tf → EC2 instance, Security Groups, User Data (install Jenkins, Docker, SonarQube, Trivy)

variables.tf → AMI ID, instance type, key pair

outputs.tf → Public IP of app

## CI/CD Pipeline (jenkins/Jenkinsfile)

**Pipeline stages:**

Checkout Code from GitHub

SonarQube Analysis

Trivy Scan (Docker image vulnerabilities)

Build & Push Docker Image → DockerHub

Deploy App to AWS EC2

## Results & Screenshots

-Terraform successfully provisioned EC2 & infra

-Jenkins pipeline executed CI/CD

-SonarQube & Trivy scans completed

-App deployed on http://<EC2-PUBLIC-IP>:3000

(Screenshots in /screenshots folder)

### Application Source Code:

Developers provided the ShopifyLite Amazon-clone app source code.

Original codebase: Amazon Clone App Repo

### My work: DevOps automation (Terraform + Jenkins)

## Conclusion

This project demonstrates how I automated the deployment pipeline for a startup application:

Infrastructure with Terraform

CI/CD with Jenkins

Quality & Security checks with SonarQube + Trivy

Containerized app delivery with DockerHub + AWS EC2

The result: ShopifyLite can release features faster, with confidence in code quality and security.
