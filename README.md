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

# Makefile for App-to-Chat Deployment

Variables - update these as per your environment
IMAGE_NAME       = app-to-chat
IMAGE_TAG        = latest
DOCKER_REGISTRY  = <your-registr>   # e.g., docker.io/kushal9897
K8S_MANIFEST_PATH = k8s/

.PHONY: all build tag push deploy compose clean

 'all' runs all main commands in sequence
all: build tag push deploy

 Build the Docker image
build:
	docker build -t $(IMAGE_NAME):$(IMAGE_TAG) .

 Tag the image for your Docker registry
tag:
	docker tag $(IMAGE_NAME):$(IMAGE_TAG) $(DOCKER_REGISTRY)/$(IMAGE_NAME):$(IMAGE_TAG)

 Push the image to your Docker registry
push:
	docker push $(DOCKER_REGISTRY)/$(IMAGE_NAME):$(IMAGE_TAG)

 Deploy to Kubernetes using your manifest files
deploy:
	kubectl apply -f $(K8S_MANIFEST_PATH)

 Optional: Run the app locally with Docker Compose
compose:
	docker-compose up -d

Optional: Tear down local Docker Compose services
clean:
	docker-compose down
