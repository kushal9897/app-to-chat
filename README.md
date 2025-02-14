# App-to-Chat

A real-time chat application built with containerized microservices, automated CI/CD pipelines, and Kubernetes orchestration. This document provides all the commands and instructions needed to build, tag, push, deploy, and manage the application in one single file.

---

## Table of Contents
- [Prerequisites](#prerequisites)
- [Setup and Installation](#setup-and-installation)
- [Usage](#usage)
  - [Docker Build and Push](#docker-build-and-push)
  - [Kubernetes Deployment](#kubernetes-deployment)
  - [Local Development with Docker Compose](#local-development-with-docker-compose)
- [Makefile Commands](#makefile-commands)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Prerequisites

- **Docker** installed on your system.
- **Kubernetes** cluster (Minikube for local testing or AWS EKS for production).
- **Terraform** (optional, if provisioning cloud resources).
- **Git** for version control.
- A Docker registry account (e.g., Docker Hub).

---

## Setup and Installation

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/kushal9897/app-to-chat.git
   cd app-to-chat
