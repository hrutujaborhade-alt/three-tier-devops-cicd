# Three-Tier DevOps CI/CD Project

End-to-end deployment and automation of a three-tier web application using Docker, AWS, Amazon ECR, Amazon EKS, Jenkins, and CI/CD practices.

## Application Overview

This project uses a three-tier web application consisting of:

- **Frontend** – HTML, CSS and JavaScript
- **Backend** – Go REST API using Gin
- **Database** – MySQL

The project focuses on containerization, cloud deployment, CI/CD automation, and operational troubleshooting.

## Architecture

The application will be progressively deployed using the following flow:

```text
Developer
    |
    v
  GitHub
    |
    v
 Jenkins
    |
    v
 Docker Build
    |
    v
 Amazon ECR
    |
    v
 Amazon EKS
    |
    +---- Frontend
    |
    +---- Backend
             |
             v
          MySQL / RDS