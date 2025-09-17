pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub-login')
        DOCKERHUB_REPO = 'anurag2426/myapp'
    }
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/anurag24-26/docker-jenkins-pipeline.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    bat 'docker build -t %DOCKERHUB_REPO%:latest .'
                }
            }
        }
        stage('Push to DockerHub') {
            steps {
                script {
                    bat "echo %DOCKERHUB_CREDENTIALS_PSW% | docker login -u %DOCKERHUB_CREDENTIALS_USR% --password-stdin"
                    bat 'docker push %DOCKERHUB_REPO%:latest'
                }
            }
        }
    }
}
