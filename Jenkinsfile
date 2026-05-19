pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps { checkout scm }
        }
        stage('Build & Test') {
            steps { sh 'echo Building project...' }
        }
        stage('Docker Build') {
            steps {
                sh 'docker build -t iffatbatool/shopcloud-frontend:latest .'
            }
        }
        stage('Docker Push') {
            steps {
                sh 'docker push iffatbatool/shopcloud-frontend:latest'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s/frontend-deployment.yaml'
            }
        }
        stage('Notification') {
            steps { echo 'Deployment Successful!' }
        }
    }
}
