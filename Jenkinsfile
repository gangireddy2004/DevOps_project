pipeline {
agent any

```
environment {
    IMAGE_NAME = "gangireddy16/my-website:v1"
}

stages {

    stage('Clone Repository') {
        steps {
            git 'https://github.com/gangireddy2004/DevOps_project.git'
        }
    }

    stage('Build Docker Image') {
        steps {
            sh 'docker build -t $IMAGE_NAME .'
        }
    }

    stage('Push Docker Image') {
        steps {
            sh 'docker push $IMAGE_NAME'
        }
    }

    stage('Deploy to Kubernetes') {
        steps {
            sh 'kubectl apply -f k8s/'
        }
    }

    stage('Verify Deployment') {
        steps {
            sh 'kubectl get pods'
        }
    }
}

post {
    success {
        echo 'Pipeline Success'
    }

    failure {
        echo 'Pipeline Failed'
    }
}
```

}
