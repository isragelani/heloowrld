pipeline {
    agent any

    environment {
        VERSION = '3.9.5'
        AUTHOR = 'Isra 🐢'
    }

    stages {
        stage('Build') {
            steps {
                echo "Building using VERSION: ${VERSION}"
                echo "Created by: ${AUTHOR}"
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }

    post {
        success {
            echo 'Build succeeded!🕺🏻'
        }
        failure {
            echo 'Build failed.💔🥀'
        }
        always {
            echo 'Post build action ran.☄️🦖'
        }
    }
}
