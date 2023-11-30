pipeline {
    agent {
        label 'slave1'
    }
    
    environment {
        DOCKER_HUB_REPO = "shuchitha/hello-world"
        CONTAINER_NAME = "hello-world"
        DOCKERHUB_CREDENTIALS=credentials('dockerhub-credentials')
    }
    
    stages {
         stage('SCM Checkout') {
            steps {
                git 'https://github.com/Shuchitha01/app1.git'
                sh 'ls -ltra'
            }
        }


          stage('Maven Build') {
            steps {
                sh "mvn -Dmaven.test.failure.ignore=true clean package"
                sh 'cd target && ls -ltra'
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'docker image build -t $DOCKER_HUB_REPO:latest .'
            }
        }
        
        stage('Push') {
            steps {
                echo 'Pushing image..'
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                sh 'docker push $DOCKER_HUB_REPO:latest'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh 'minikube kubectl -- apply -f deployment.yaml'
                sh 'minikube kubectl -- apply -f service.yaml'
            }
        }
    }
}