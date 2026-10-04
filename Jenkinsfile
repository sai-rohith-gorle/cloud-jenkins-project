pipeline {

    agent any

    stages {

        stage('Clone') {
    steps {
        git 'https://github.com/sai-rohith-gorle/cloud-jenkins-project.git'
    }
}

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t cloud-web-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop cloud-web-app || true'
                sh 'docker rm cloud-web-app || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d --name cloud-web-app -p 80:80 cloud-web-app'
            }
        }
    }
}
