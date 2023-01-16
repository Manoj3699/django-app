pipeline{
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials ('django-docker')    
        IMAGE_TAG="latest"
    }
    stages {
        stage('Code Clone'){
            steps{
                git branch: 'main', credentialsId: '235eaeec-3444-4478-9f7b-622055af9bf0', url: 'https://github.com/Manoj3699/django-app.git'
            }
        }
        stage('Docker Build'){
            steps{
                sh 'sudo docker build -t django-todo:$IMAGE_TAG .'
            }
        }
        stage('Push Image') {
            steps{
                sh 'sudo docker login -u manoj3699 -p manoj3699'
                sh 'sudo docker push manoj3699/django-todo:$IMAGE_TAG'
            }
        }
    }    
}    
