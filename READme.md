# Yolo Project

## Overview

This project demonstrates the deployment of a web application using Kubernetes on Google Kubernetes Engine (GKE). The application consists of a frontend and backend service, both of which are built as Docker images and hosted on Docker Hub.

## Prerequisites

- Google Cloud Platform (GCP) account
- Google Cloud SDK (gcloud) installed
- Kubernetes command-line tool (kubectl) installed
- Docker installed

## Setup Instructions

### Step 1: Clone the Repository

```sh
git clone <repository-url>
cd <repository-directory>
Step 2: Set Up GCP Project
Set your GCP project ID:

sh
Copy code
gcloud config set project <your-gcp-project-id>
Step 3: Authenticate with GCP
Authenticate your GCP account:

sh
Copy code
gcloud auth login
gcloud auth application-default login
Step 4: Create a GKE Cluster
Create a GKE cluster:

sh
Copy code
gcloud container clusters create my-cluster --zone us-central1-a --num-nodes=3
Step 5: Get Cluster Credentials
Get the credentials for your GKE cluster:

sh
Copy code
gcloud container clusters get-credentials my-cluster --zone us-central1-a
Step 6: Deploy Backend
Apply the backend deployment and service YAML files:

sh
Copy code
kubectl apply -f backend-deployment.yaml
kubectl apply -f backend-service.yaml
Step 7: Deploy Frontend
Apply the frontend deployment and service YAML files:

sh
Copy code
kubectl apply -f frontend-deployment.yaml
kubectl apply -f frontend-service.yaml
Step 8: Deploy Database (Postgres) with StatefulSet
Apply the Postgres StatefulSet and service YAML files:

sh
Copy code
kubectl apply -f postgres-statefulset.yaml
kubectl apply -f postgres-service.yaml
Step 9: Verify Deployments
Check the status of your deployments:

sh
Copy code
kubectl get pods
kubectl get services
Step 10: Access the Application
Find the external IP of the frontend service:

sh
Copy code
kubectl get services
Access the application at: http://<external-ip>

Live URL
Access the application at: http://<external-ip>

