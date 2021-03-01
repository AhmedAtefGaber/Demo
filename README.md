# Demo
this is a demo project in the realm of containers and microservices
trying to automate the build and deployment of a simple application.

## Dockerfile
A simple Dockerfile, based on nginx:alpine.
editing the index.html page so the response of the app will be “Hello, this is Ahmed”
changing the application’s port to 8083
Pushing the same hello message and hostname info to stdout of the container every 1 minute.

## Jenkinsfile
Using Jenkins to automate the build process of the docker image, push the image to Docker hub.
then deploy the web application to a Kubernetes cluster and access it through a node port service.

## resources
It contains the yamls of the Kubernetes resources that will be deployed, scripts need for the cron job in 
the container and Nginx, and index.html