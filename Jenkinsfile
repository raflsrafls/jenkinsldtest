pipeline {
    agent any
    stages {
        stage('install-pip-deps') {
            steps {
                // Clone the repository
                powershell 'git clone https://github.com/mtararujs/python-greetings'

                // Check for the existence of required files if necessary
                powershell 'ls python-greetings\\required_files'

                // Install the necessary libraries
                powershell 'pip install -r python-greetings\\requirements.txt'
                
                echo 'Hello World'
            }
        }
      stage('deploy-to-dev') {
            steps {
                echo 'Deploying to dev...'
            }
        }
      stage('tests-on-dev') {
            steps {
                echo 'Testing on dev'
            }
        }
      stage('deploy-to-staging') {
            steps {
                echo 'Deploying to staging'
            }
        }
      stage('tests-on-preprod') {
            steps {
                echo 'Testing on prepod'
            }
        }
      stage('deploy-to-prod') {
            steps {
                echo 'Deploying to prod'
            }
        }
      stage('tests-on-prod') {
            steps {
                echo 'Testing on prod'
            }
        }
    }
}