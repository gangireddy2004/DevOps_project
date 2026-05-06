pipeline {
    agent any

    stages {

        stage('Check Docker') {
            steps {
                sh 'docker --version'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-website .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop my-container || true'
                sh 'docker rm my-container || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d -p 8081:80 --name my-container my-website'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker tag my-website gangireddy16/my-website:v1'
                sh 'docker push gangireddy16/my-website:v1'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f K8s/'
            }
        }

        stage('Verify Deployment') {
            steps {
                sh 'kubectl get pods'
                sh 'kubectl get svc'
            }
        }

        stage('Check Running Containers') {
            steps {
                sh 'docker ps'
            }
        }
    }

    post {

        success {
            echo 'CI/CD Pipeline Executed Successfully'
        }

        failure {
            echo 'Pipeline Failed'
        }
    }
}