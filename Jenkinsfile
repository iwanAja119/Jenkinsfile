pipeline {
    agent any
    environment {
        IMAGE_NAME = 'ihs4n/simple-app'
        REGISTRY_CREDENTIALS = 'dockerhub-credentials'
        DOCKER_BIN = 'C:\\Program Files\\Docker\\Docker\\resources\\bin\\docker.exe'
    }
    stages {
        stage('Checkout') {
            steps { checkout scm }
        }
        stage('Build') {
            steps { bat 'echo "Build di windows"' }
        }
        stage('Build Docker Image') {
            steps {
                bat '"%DOCKER_BIN%" build -t %IMAGE_NAME%:%BUILD_NUMBER% .'
            }
        }
        stage('Push Docker Image') {
            steps {
                withCredentials([usernamePassword(credentialsId: REGISTRY_CREDENTIALS,
                    usernameVariable: 'USER', passwordVariable: 'PASS')]) {
                    bat '"%DOCKER_BIN%" login -u %USER% -p %PASS%'
                    bat '"%DOCKER_BIN%" push %IMAGE_NAME%:%BUILD_NUMBER%'
                    bat '"%DOCKER_BIN%" tag %IMAGE_NAME%:%BUILD_NUMBER% %IMAGE_NAME%:latest'
                    bat '"%DOCKER_BIN%" push %IMAGE_NAME%:latest'
                }
            }
        }
    }
}
