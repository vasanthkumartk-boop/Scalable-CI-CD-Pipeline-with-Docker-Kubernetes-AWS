pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "vasanthsir/ci-cd-app"
    }

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/vasanthkumartk-boop/Scalable-CI-CD-Pipeline-with-Docker-Kubernetes-AWS.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE ./app'
            }
        }

        stage('Push to DockerHub') {
            steps {
                withCredentials([string(credentialsId: 'dockerhub-password', variable: 'PASSWORD')]) {
                    sh 'echo $PASSWORD | docker login -u vasanthsir --password-stdin'
                    sh 'docker push $DOCKER_IMAGE'
                }
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s/'
            }
        }
    }
}
