# Kubernetes Web App with MongoDB Deployment using Minikube

This project demonstrates the deployment of a web application and MongoDB in a Kubernetes cluster using Minikube. The deployment includes ConfigMaps and Secrets for managing configuration data securely.

# Table of Contents

- [Overview](#overview)
- [Project Structure](#project-structure)
- [Deployment Steps](#deployment-steps)
- [Configuration](#configuration)
- [Usage](#usage)
- [Author](#author)
- [License](#license)


oVERVIEW
## Overview

This project showcases the deployment of a web application and MongoDB in a Kubernetes environment. It utilizes ConfigMaps for configuration management and Secrets for handling sensitive information. The deployment is orchestrated using Minikube, making it easy to test and showcase on a local Kubernetes cluster.


## Project Structure

- `mongo-config.yaml`: ConfigMap for MongoDB configuration.
- `secret-mongo.yaml`: Secret for MongoDB credentials.
- `mongo.yaml`: Deployment and Service configuration for MongoDB.
- `webapp.yaml`: Deployment and Service configuration for the web application.


## Deployment Steps

1. Apply MongoDB ConfigMap and Secret:
   ```bash
   kubectl apply -f configmap-mongo.yaml
   kubectl apply -f secret-mongo.yaml

 kubectl apply -f mongo.yaml


kubectl apply -f webapp.yaml


kubectl expose deployment mongo-deployment --type=ClusterIP --name=mongo-service
kubectl expose deployment webapp-deployment --type=NodePort --name=webapp-service
