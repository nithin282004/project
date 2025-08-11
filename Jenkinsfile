pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'docker build -t myapp .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                bat 'docker tag myapp username/myapp:latest'
                bat 'docker push username/myapp:latest'
            }
        }
        stage('Deploy to K8s') {
            steps {
                bat 'kubectl apply -f k8s/deployment.yaml'
            }
        }
    }
}
