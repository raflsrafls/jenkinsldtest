pipeline {
    agent any
    
    stages {
        stage('install-pip-deps') {
            steps {
                powershell 'git clone https://github.com/mtararujs/python-greetings'

                powershell 'ls python-greetings'

                powershell 'pip install -r python-greetings\\requirements.txt'
                
                echo 'Hello World'
            }
        }
        stage('deploy-to-dev') {
            steps {
                echo 'Deployment to DEV has started..'
            }
        }
        stage('tests-on-dev') {
            steps {
                echo 'Testing on DEV has started..'
            }
        }
        stage('deploy-to-staging') {
            steps {
                echo 'Deployment to STG has started..'
            }
        }
        stage('tests-on-staging') {
            steps {
                echo 'Testing on STG has started..'
            }
        }
        stage('deploy-to-preprod') {
            steps {
                echo 'Deployment to PRD has started..'
            }
        }
        stage('tests-on-preprod') {
            steps {
                echo 'Testing on PRD has started..'
            }
        }
        stage('deploy-to-prod') {
            steps {
                echo 'Testing on PRD has started..'
            }
        }
        stage('tests-on-prod') {
            steps {
                echo 'Testing on PRD has started..'
            }
        }
    }
}