pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/YOUR-USERNAME/devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop devops-container || true'
                sh 'docker rm devops-container || true'
                sh 'docker run -d -p 5000:5000 --name devops-container devops-app'
            }
        }
    }
}
