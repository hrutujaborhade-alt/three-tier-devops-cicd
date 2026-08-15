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


## Dockerfiles

The application is containerized using separate Dockerfiles for the backend and frontend.

### Backend Dockerfile

The backend uses a multi-stage Docker build. The Go application is compiled in a builder image and only the required binary is copied to the final lightweight image, reducing the final image size.

**Dockerfile:** `backend/Dockerfile`

---

### Frontend Dockerfile

The frontend uses Nginx to serve the application static files. The Docker image provides a lightweight web server for the frontend and is later configured as a reverse proxy for backend API requests.

**Dockerfile:** `frontend/Dockerfile`

---

### Docker Images Created

The following images were created and tested on the EC2 test server:

```text
skillpulse-backend:1.0
skillpulse-frontend:1.0
mysql:8.4
