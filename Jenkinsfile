pipeline {
    agent any

    stages {

        stage('Check Docker') {
            steps {
                bat 'docker --version'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t my-website .'
            }
        }

        stage('Stop Old Container') {
            steps {
                bat 'docker stop my-container || exit 0'
                bat 'docker rm my-container || exit 0'
            }
        }

        stage('Run New Container') {
            steps {
                bat 'docker run -d -p 8081:80 --name my-container my-website'
            }
        }

        stage('Check Running Containers') {
            steps {
                bat 'docker ps'
            }
        }
    }
}