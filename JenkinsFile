pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                // Here you can define commands for your build, like:
                // sh 'npm install' or sh 'make'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing..'
                // Put test commands here, e.g.
                // sh 'pytest tests/' or sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying....'
                // Deployment steps go here
                // sh 'scp app user@server:/path/'
            }
        }
    }
}

