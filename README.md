# Brain Tasks App – DevOps Project 3

## Project Overview

This project demonstrates the deployment of the Brain Tasks React application using a production-oriented DevOps workflow.

The application is containerized using Docker, stored in Amazon Elastic Container Registry (ECR), deployed to Amazon Elastic Kubernetes Service (EKS), and automated using AWS CodeBuild and AWS CodePipeline.

## Architecture

GitHub
   |
   v
AWS CodePipeline
   |
   v
AWS CodeBuild
   |
   +----> Docker Build
   |
   +----> Amazon ECR
   |
   v
Amazon EKS
   |
   v
Kubernetes Deployment
   |
   v
Kubernetes LoadBalancer
   |
   v
Brain Tasks Application

## Technologies Used

- GitHub
- Git
- Docker
- Amazon ECR
- Amazon EKS
- Kubernetes
- kubectl
- AWS CodeBuild
- AWS CodePipeline
- Amazon CloudWatch
- Nginx
- React production build

## Repository Structure

```text
Brain-Tasks-App/
├── dist/
│   ├── assets/
│   ├── index.html
│   └── vite.svg
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
├── Dockerfile
├── buildspec.yml
└── README.mdT
## Deployment Details

### AWS Resources

- AWS Region: ap-south-1 (Mumbai)
- Amazon ECR Repository: brain-tasks-app
- Amazon EKS Cluster: project3-devops-eks
- Kubernetes Deployment: brain-tasks-app
- Kubernetes Service: brain-tasks-service
- Service Type: LoadBalancer
- Load Balancer Scheme: Internet-facing
- Load Balancer Port: 80

### Kubernetes Load Balancer

Load Balancer DNS:
k8s-default-braintasks-1bd5849aad-ae40a02db693e5e5.elb.ap-south-1.amazonaws.com

Load Balancer ARN:
arn:aws:elasticloadbalancing:ap-south-1:938358605650:loadbalancer/net/k8s-default-braintasks-1bd5849aad/ae40a02db693e5e5

### CI/CD Pipeline

GitHub → AWS CodePipeline → AWS CodeBuild → Amazon ECR → Amazon EKS → Kubernetes LoadBalancer

The CodeBuild project builds the Docker image, pushes the image to Amazon ECR, configures kubectl for Amazon EKS, updates the Kubernetes deployment, and applies the Kubernetes service configuration.

### Monitoring

AWS CloudWatch Logs are configured for:
- AWS CodeBuild
- Amazon EKS cluster

The successful CodeBuild execution and Kubernetes deployment are available in CloudWatch Logs.
