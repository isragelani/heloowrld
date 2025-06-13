pipeline {
    agent any

    environment {
        VERSION = '3.9.5'
    }

    parameters {
        booleanParam(name: 'RUN_TEST', defaultValue: true, description: 'Run the Test Stage?')
        choice(name: 'CHOICE_VERSION', choices: ['3.8.7', '3.9.5', '4.0.0'], description: 'Choose your version')
    }

    tools {
        maven 'Maven'
    }

    stages {
        stage('Build') {
            steps {
                echo "Building using Maven version: ${VERSION} (User selected: ${params.CHOICE_VERSION})"
            }
        }

        stage('Test') {
            when {
                expression {
                    return params.RUN_TEST == true
                }
            }
            steps {
                echo 'Running Tests...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying App...'
            }
        }
    }

    post {
        success {
            echo 'Build succeeded!🕺🏻'
        }
        failure
        {
            echo 'Build failed. Please check logs.🥀💔'
        }
        always
        {
            echo 'Post build action running, no matter what.🦖☄️'
        }
    }
}
