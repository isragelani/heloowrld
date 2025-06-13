pipeline {
    agent any

    environment {
        VERSION = '3.9.5'
        AUTHOR = 'Isra 🐢'
    }

    tools {
        maven 'Maven'
    }

    stages {
        stage('Build') {
            steps {
                echo "Building using Maven version: ${VERSION}"
                echo "Created by: ${AUTHOR}"

                bat 'mvn --version'
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
