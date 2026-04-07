pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/vasanthkumartk-boop/Scalable-CI-CD-Pipeline-with-Docker-Kubernetes-AWS.git'
            }
    }

      stage('Build Docker Image') {
    steps {
        sh 'docker build -t vasanthsir/devops-app .'

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t  vasanthsir/devops-app .'
 ( update a Jenkins file)
            }
        }	

        stage('Push to DockerHub') {
            steps {
                sh 'vasanthsir/devops-app'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s/'
            }
        }
    }
}
stage('Debug Files') {
    steps {
        sh 'pwd'
        sh 'ls -la'
    }
}
