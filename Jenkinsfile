pipeline
{
    agent any

    parameters
    {
        booleanParam(name: 'RUN_TEST', defaultValue: true, description: 'Run the Test Stage?')
    }

    stages {
        stage('Build')
        {
            steps
            {
                echo 'Building...'
            }
        }

        stage('Test')
        {
            when
            {
                expression
                {
                    return params.RUN_TEST == true }
            }
            steps
            {
                echo 'Testing...'

            }
        }

        stage('Deploy')
        {
            steps
            {
                echo 'Deploying...'
            }
        }
    }

    post
    {
        success
        {
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
