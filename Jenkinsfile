pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t automated-web-app:latest .'
            }
        }

        stage('Test Docker Image') {
            steps {
                bat 'docker run -d --name automated-web-app-test -p 8081:80 automated-web-app:latest'
            }
        }

        stage('Stop Test Container') {
            steps {
                bat 'docker stop automated-web-app-test'
                bat 'docker rm automated-web-app-test'
            }
        }

        stage('Deploy Using Ansible') {
            steps {
                bat 'ansible-playbook -i ansible/inventory ansible/deploy.yml'
            }
        }
    }

    post {
        success {
            echo 'Deployment completed successfully!'
        }

        failure {
            echo 'Deployment failed!'
        }
    }
}