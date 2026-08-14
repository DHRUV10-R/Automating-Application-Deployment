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
                bat 'dir'
            }
        }

        stage('Test') {
            steps {
                echo 'Running basic project verification...'
                bat 'dir app'
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