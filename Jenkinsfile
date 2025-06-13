pipeline {
    agent any

    parameters {
        string(name: 'VERSION', defaultValue: '1.1.0', description: 'Version to deploy on prod')
        choice(name: 'CHOICE_VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: 'Select a version')
        booleanParam(name: 'EXECUTE_TESTS', defaultValue: true, description: 'Run the Test Stage?')
    }

    environment {
        AUTHOR = 'Isra 🐢'
    }

    tools {
        maven 'Maven'
    }

    stages {
        stage('Build') {
            steps {
                echo "Building with selected VERSION: ${params.VERSION}"
                echo "Choice version selected: ${params.CHOICE_VERSION}"
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
                echo 'Running tests because EXECUTE_TESTS is true ✅'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying version: ${params.VERSION} (Choice: ${params.CHOICE_VERSION})"
            }
        }
    }

    post {
        success {
            echo '✅ Build succeeded!🕺🏻'
        }
        failure {
            echo '❌ Build failed.💔🥀'
        }
        always {
            echo '☄️ Post build action ran no matter what.🦖'
        }
    }
}
