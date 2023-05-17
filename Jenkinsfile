pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Clone the repository
                powershell 'git clone https://github.com/mtararujs/python-greetings'

                // Check for the existence of required files if necessary
                powershell 'ls python-greetings\\required_files'

                // Install the necessary libraries
                powershell 'pip3 install -r python-greetings\\requirements.txt'
                
                echo 'Hello World'
            }
        }
        stage('Deploy to DEV') {
            steps {
                echo 'Deployment to DEV has started..'
            }
        }
        stage('Tests on DEV') {
            steps {
                echo 'Testing on DEV has started..'
            }
        }
        stage('Deploy to STG') {
            steps {
                echo 'Deployment to STG has started..'
            }
        }
        stage('Tests on STG') {
            steps {
                echo 'Testing on STG has started..'
            }
        }
        stage('Deploy to PRD') {
            steps {
                echo 'Deployment to PRD has started..'
            }
        }
        stage('Tests on PRD') {
            steps {
                echo 'Testing on PRD has started..'
            }
        }
    }
}