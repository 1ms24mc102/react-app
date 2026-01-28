pipeline {
    agent any

    environment {
        IMAGE_NAME = "1ms24mc102/react_app"
        DOCKER_CREDENTIALS = "dockerHub"
    }

    stages {

        stage('Link Git Repository') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/1ms24mc102/react-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("${IMAGE_NAME}:latest")
                }
            }
        }

        stage('Push Image to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('', DOCKER_CREDENTIALS) {
                        dockerImage.push("latest")
                    }
                }
            }
        }
    }
}
