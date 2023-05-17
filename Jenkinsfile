pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                powershell 'git clone https://github.com/mtararujs/python-greetings'

                powershell 'ls python-greetings'

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