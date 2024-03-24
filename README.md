# Mediawiki_TW
This chapter describes the prerequisites, best practices, parameters, and procedures used to install Mediawiki(v.1.35)
It will deploy Mediawiki applciation with integration of mysql database.
# Prerequisites
- kubernetes (tested on kubernets version= v1.26.4)
- kubectl client
- Helm 

# Parameters
All the environment variables(paramters) placed in mediawiki>values.yaml please change them if needed.

# Installation
Please follow below steps to deploy mediawiki application
1. Clone this repo to your local machine
2. login to your kubernetes cluster before execution of  deployment
3. make sure to update bluegreen deployment true or false as optional in the values.yaml file.
4. use this command to deploy applciation along with db "helm install <package name> ./mediawiki -n <namespace in k8s>"
5. verify if all created resources using "kubectl get all -n <namespace in k8s>"
6. get ingress url using kubeclt get ingress -n <namespace in k8s> to access the applciation.
# Devloper guide
- This document will help you to dpeloy meidawiki 1.35 version if you need any specific version need to build custom Docker images.
- to create custom docker image for mediawiki,please update the Dockerfile which is placed in docker-custom-image.
- Build the new docker image with updated dockerfile using "docker build -t <image-name> <path-to-Dockerfile>"
- push the new image to your docker repo or any repository
- change the repo and tag details in the values.yaml and follow the Intsllaiton document.
# images
