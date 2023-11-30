hello-world-devops-project........................
Build and deploy code a simple application using Jenkins and Kubernetes.
In this project, we are going to build a simple devops project, Docker, Git, Github, Jenkins and Kubernetes.

###Prerequisites
* Python
* Flask
* Docker
* Git and Github
* Jenkins

## Steps in the CI/CD pipeline
1. Create a "Hello world" Flask application
2. Dockerise the application
3. Create a github repository and push code to it
4. Start a Jenkins server on a host
5. Write a Jenkins pipeline to build, test and push the docker image to Dockerhub.
6. Set up Kubernetes on a host using [Minikube]
7. Create a Kubernetes deployment and service for the application.
8. Use Jenkins to deploy the application on Kubernetes


 
## Project structure
 
* app.py - Flask application which will print "Hello world" when you run it
* Dockerfile - Contains commands to build and run the docker image
* Jenkinsfile - Contains the pipeline script which will help in building, testing and deploying the application
* deployment.yaml - file for the application
* service.yaml -  file for the application





### Used grafrana and promethues
Grafana-  contains monnitoring the dashbioard.
promethues
