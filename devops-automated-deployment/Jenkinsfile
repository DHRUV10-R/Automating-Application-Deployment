pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code from GitHub...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Checking project files...'
                sh 'pwd'
                sh 'ls -la'
                sh 'ls -la app'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing application files...'

                sh 'test -f app/index.html'
                sh 'test -f app/style.css'

                echo 'Application files verified successfully.'
            }
        }
    }

    post {

        success {
            echo '========================================='
            echo 'GITHUB -> JENKINS SUCCESS'
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