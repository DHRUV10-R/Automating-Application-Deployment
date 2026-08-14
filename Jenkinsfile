pipeline {
    agent any

    stages {

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

        // Docker stage
        // Ansible deployment stage
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