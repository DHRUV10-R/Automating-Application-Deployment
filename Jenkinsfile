pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Checking project files...'
                bat 'dir'
                bat 'dir app'
            }
        }

        stage('Test') {
            steps {
                echo 'Running basic project verification...'
                bat 'dir app'
            }
        }

        stage('Docker Build') {
            steps {
                echo 'Building Docker image...'
                bat 'docker build -t automated-web-app:latest .'
            }
        }

        stage('Docker Test') {
            steps {
                echo 'Checking Docker image...'
                bat 'docker images automated-web-app'
            }
        }
    }

    post {
        success {
            echo '========================================='
            echo 'PIPELINE SUCCESSFUL'
            echo '========================================='
        }

        failure {
            echo '========================================='
            echo 'PIPELINE FAILED'
            echo 'Check the Jenkins console output.'
            echo '========================================='
        }
    }
}