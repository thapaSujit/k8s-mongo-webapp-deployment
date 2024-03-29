# Kubernetes Web App with MongoDB Deployment using Minikube

# Table of Contents

- [Overview](#overview)
- [Project Structure](#project-structure)
- [Deployment Steps](#deployment-steps)
- [Links](#Links)
- [Acknowledgments](#Acknowledgments)

## Overview

This project showcases the deployment of a web application and MongoDB in a Kubernetes environment. It utilizes ConfigMaps for configuration management and Secrets for handling sensitive information. The deployment is orchestrated using Minikube, making it easy to test and showcase on a local Kubernetes cluster.


## Project Structure

- `mongo-config.yaml`: ConfigMap for MongoDB configuration.
- `secret-mongo.yaml`: Secret for MongoDB credentials.
- `mongo.yaml`: Deployment and Service configuration for MongoDB.
- `webapp.yaml`: Deployment and Service configuration for the web application.


## Deployment Steps
1. Start the minikube cluster 
```bash
   minikube start --driver docker 
   minikube status
   ```

2. Apply MongoDB ConfigMap and Secret:
```bash
   kubectl apply -f configmap-mongo.yaml
   kubectl apply -f secret-mongo.yaml
   kubectl apply -f mongo.yaml
   kubectl apply -f webapp.yaml
   ```
3. Get the node's ip address
```bash
    minikube ip
   ```
4. Use that node ip address and the port of the external service node which is 30100(See webapp.yaml file) to access the app in your browser

5. stop your Minikube cluster
```bash
    minikube stop

   ```

## Links
 - Webapp Image on Docker Hub : https://hub.docker.com/repository/docker/nanajanashia/k8s-demo-app

## Acknowledgments

I would like to express my gratitude to TechWorld with Nana for creating an incredibly helpful video that greatly assisted me in understanding K8.

[Link to the Helpful Video](https://www.youtube.com/watch?v=s_o8dwzRlu4)

