# Mediawiki_TW
This repository contains instructions and configurations for deploying Mediawiki (version 1.35) integrated with MySQL database on Kubernetes.
# Prerequisites
Ensure the following prerequisites are met before deploying Mediawiki:
- kubernetes (tested on kubernets version= v1.26.4)
- kubectl client
- Helm 

# Parameters
All the environment variables (parameters) are located in `mediawiki/values.yaml`. Modify them as needed.

# Installation
Follow these steps to deploy Mediawiki application:
1. Clone this repository to your local machine.
2. Log in to your Kubernetes cluster before executing the deployment.
3. Ensure to update the `bluegreen` deployment flag as `true` or `false` (optional) in the `values.yaml` file.
4. Use the following command to deploy the application along with the database:      
 ```helm install <package name> ./mediawiki -n <namespace in k8s>```
5. Verify if all resources are created using: ```kubectl get all -n <namespace in k8s>```
6. Retrieve the ingress URL using: ```kubeclt get ingress -n <namespace in k8s>``` This URL can be used to access the application.
# Developer Guide
This section provides guidelines for deploying Mediawiki specific version  and building custom Docker images:
- To deploy a specific version of Mediawiki, update the Dockerfile located in `docker-custom-image`.
- Build the new Docker image with the updated Dockerfile using: ```docker build -t <image-name> <path-to-Dockerfile>```
- Push the new image to your Docker repository or any other repository.
- Update the repository and tag details in the values.yaml file and follow the installation document.
# images

![alt text](https://github.com/satyamguntha/Mediawiki_TW/blob/main/images/app%26db.jpg)
![alt text](https://github.com/satyamguntha/Mediawiki_TW/blob/main/images/pvc's.jpg)
![alt text](https://github.com/satyamguntha/Mediawiki_TW/blob/main/images/ingress.jpg)
![alt text](https://github.com/satyamguntha/Mediawiki_TW/blob/main/images/mediawiki1.jpg)
![alt text](https://github.com/satyamguntha/Mediawiki_TW/blob/main/images/mediawiki2.jpg)


