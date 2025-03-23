pipeline {
    agent any
    environment {
        DOCKER_IMAGE = "kediaharsh/studentproject"
    }
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Harshvardhan011-k/Django-app.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                withDockerRegistry([credentialsId: 'docker-hub-credentials']) {
                    sh 'docker push $DOCKER_IMAGE'
                }
            }
        }
    }
}
