pipeline {
    agent any

    environment {
        VERSION = '3.9.5'
        AUTHOR = 'Isra 🐢'
    }

    tools {
        maven 'Maven'
    }
    parameters {
        booleanParam(name: 'EXECUTE_TESTS', defaultValue: true, description: 'Run the Test Stage?')
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
            when {
                expression {
                    return params.EXECUTE_TESTS == true
                }
            }
            steps {
                echo 'Testing... (because EXECUTE_TESTS is true ✅)'
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
