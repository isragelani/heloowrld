pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // e.g., sh 'javac helooWrld.java'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
                // e.g., sh 'java helooWrld'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Placeholder deploy logic
            }
        }
    }

    post {
        success {
            echo 'Build succeeded!🕺🏻'
        }
        failure {
            echo 'Build failed. Please check logs.🥀💔'
        }
        always {
            echo 'Post build action running, no matter what.🦖☄️'
        }
    }
}
