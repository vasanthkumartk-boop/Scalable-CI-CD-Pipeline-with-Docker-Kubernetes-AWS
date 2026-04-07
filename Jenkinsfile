pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "your-dockerhub-username/ci-cd-app"
    }

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/your-username/ci-cd-pipeline-project.git'
            }
    }


      stage('Build Docker Image') {
    steps {
        sh 'docker build -t vasanthsir/devops-app .'

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t  vasanthsir/devops-app .'
 ( update a Jenkins file)

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE ./app'
( update and edit the file)
            }
        }

        stage('Push to DockerHub') {
            steps {
                withCredentials([string(credentialsId: 'dockerhub-password', variable: 'PASSWORD')]) {
                    sh 'echo $PASSWORD | docker login -u vasanthsir  --password-stdin'
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






