pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                echo 'Code Cloned'
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

                sh 'docker run -dit --name devops-container devops-app'
            }
        }
    }
}
