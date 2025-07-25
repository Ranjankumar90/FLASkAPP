# Auto-Deploy Flask App on AWS ECS

## Overview
This project demonstrates how to containerize a Flask app, deploy it to AWS ECS using Terraform, automate builds with Jenkins, monitor with Nagios, and integrate CI/CD with GitHub Actions.

## Structure
- `app.py`: Basic Flask application
- `requirements.txt`: Python dependencies
- `Dockerfile`: Containerization instructions
- `main.tf`, `variables.tf`, `ecs.tf`, `vpc.tf`: Terraform configs for AWS ECS
- `.github/workflows/main.yml`: GitHub Actions workflow
- `Jenkinsfile`: Jenkins pipeline

## Setup

### 1. Flask App
- Edit `app.py` as needed.
- Install dependencies: `pip install -r requirements.txt`

### 2. Docker
- Build: `docker build -t flask-ecs-app .`
- Run: `docker run -p 5000:5000 flask-ecs-app`

### 3. Terraform (AWS ECS)
- Configure AWS credentials.
- `terraform init`
- `terraform plan`
- `terraform apply`

### 4. Jenkins
- Set up Jenkins with Docker and AWS plugins.
- Use `Jenkinsfile` for pipeline.

### 5. GitHub Actions
- Workflow in `.github/workflows/main.yml` handles lint, build, push, and notifications.

### 6. Nagios Monitoring
- Install Nagios on a monitoring server.
- Monitor ECS endpoint and EC2 metrics.

## Notes
- Update AWS, ECR, and Terraform details as needed.
- Secure secrets using GitHub and Jenkins credential stores. 