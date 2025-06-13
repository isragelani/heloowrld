pipeline {
    agent any

    // 👇 Add this to allow a toggle for running the Test stage
    parameters {
        booleanParam(defaultValue: true, description: 'Run the Test stage?', name: 'RUN_TESTS')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // e.g., sh 'javac helooWrld.java'
            }
        }

        stage('Test') {
            // 👇 Conditional execution based on RUN_TESTS
            when {
                expression { return params.RUN_TESTS == true }
            }
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
