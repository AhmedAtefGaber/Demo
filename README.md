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

## Auto scale application in the Kubernetes cluster
Configuring the Kubernetes cluster to scale the given application up when it gets heavy load. 
Then, generate a heavy load and observe the application is scaled up.

```bash
kubectl autoscale deployment app-deployment -n web-app --cpu-percent=10 --min=1 --max=10
kubectl run -i --tty load-generator --rm --image=busybox --restart=Never -- /bin/sh -c "while sleep 0.01; do wget -q -O- http://node1:32083; done"
watch -x kubectl get hpa -n web-app
watch -x kubectl get pods -n web-app
```