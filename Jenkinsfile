pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t myapp .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                sh 'docker tag myapp username/myapp:latest'
                sh 'docker push username/myapp:latest'
            }
        }
        stage('Deploy to K8s') {
            steps {
                sh 'kubectl apply -f k8s/deployment.yaml'
            }
        }
    }
}
