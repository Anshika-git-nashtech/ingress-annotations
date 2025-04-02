# Deploying a Python App with NGINX Ingress and annotations on Kubernetes

This repository contains the necessary configuration files to set up a Python application inside a Kubernetes cluster using a Dockerfile and an Ingress object with specific NGINX annotations.

## Prerequisites

Ensure you have the following installed:

- Minikube / GKE / EKS (or any Kubernetes cluster)
- kubectl (Kubernetes CLI)
- NGINX Ingress Controller installed in the cluster

## Clone the Repository

    git clone <repository_url>
    cd <repository_name>

##  Build and Push Docker Image

    docker build -t <your-dockerhub-username>/my-app:latest .
    docker push <your-dockerhub-username>/my-app:latest

##  Deploy the Application

     kubectl apply -f deploy.yaml
     kubectl apply -f service.yaml
     kubectl apply -f ingress.yaml

## Verify Deployment

Check if the ingress is created:

      kubectl get pods
            
Check if the ingress is created:

      kubectl get ingress

## Access the Application

If using Minikube, run:

      minikube service list

If using an external Kubernetes cluster, access via the assigned Ingress URL.

You can make changes in this template by editing deploy.yaml, service.yaml, or ingress.yaml to suit your application needs.
