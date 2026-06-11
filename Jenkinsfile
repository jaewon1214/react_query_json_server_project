pipeline {

    agent any

    stages {

        stage('Git Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Docker Compose Build') {
            steps {
                sh '''
                docker compose build
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                docker compose down || true
                docker compose up -d --build
                '''
            }
        }

        stage('Check Container') {
            steps {
                sh '''
                docker ps
                '''
            }
        }
    }

    post {

        success {
            echo '================================='
            echo 'Deployment Success'
            echo '================================='
        }

        failure {
            echo '================================='
            echo 'Deployment Failed'
            echo '================================='
        }
    }
}