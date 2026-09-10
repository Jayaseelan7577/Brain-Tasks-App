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
