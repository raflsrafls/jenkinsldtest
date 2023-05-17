pipeline {
    agent any
    
    stages {
        stage('install-pip-deps') {
            steps {
                powershell 'git clone https://github.com/mtararujs/python-greetings'

                powershell 'ls python-greetings'

                powershell 'pip install -r python-greetings\\requirements.txt'
                
                echo 'Installing PIP has started ...'
            }
        }
        stage('deploy-to-dev') {
            steps {
                powershell 'git clone https://github.com/mtararujs/python-greetings'

                powershell 'pm2 delete greetings-app-dev & set "errorlevel=0"'

                powershell 'pm2 start app.py --name greetings-app-dev -- --port 7001'

                echo 'Deployment to DEV has started..'
            }
        }
        stage('tests-on-dev') {
            steps {
                powershell 'git clone https://github.com/mtararujs/course-js-api-framework'

                powershell 'npm install'

                powershell 'npm run greetings greetings_dev'

                echo 'Testing on DEV has started..'
            }
        }
        stage('deploy-to-staging') {
            steps {
                powershell 'git clone https://github.com/mtararujs/python-greetings'

                powershell 'pm2 delete greetings-app-staging & set "errorlevel=0"'

                powershell 'pm2 start app.py --name greetings-app-staging -- --port 7002'

                echo 'Deployment to STG has started..'
            }
        }
        stage('tests-on-staging') {
            steps {
                powershell 'git clone https://github.com/mtararujs/course-js-api-framework'

                powershell 'npm install'

                powershell 'npm run greetings greetings_staging'
                
                echo 'Testing on STG has started..'
            }
        }
        stage('deploy-to-preprod') {
            steps {
                powershell 'git clone https://github.com/mtararujs/python-greetings'

                powershell 'pm2 delete greetings-app-preprod & set "errorlevel=0"'

                powershell 'pm2 start app.py --name greetings-app-preprod -- --port 7003'

                echo 'Deployment to PRD has started..'
            }
        }
        stage('tests-on-preprod') {
            steps {
                powershell 'git clone https://github.com/mtararujs/course-js-api-framework'

                powershell 'npm install'

                powershell 'npm run greetings greetings_preprod'
                
                echo 'Testing on PRD has started..'
            }
        }
        stage('deploy-to-prod') {
            steps {
                powershell 'git clone https://github.com/mtararujs/python-greetings'

                powershell 'pm2 delete greetings-app-prod & set "errorlevel=0"'

                powershell 'pm2 start app.py --name greetings-app-prod -- --port 7004'

                echo 'Deployment to PROD has started..'
            }
        }
        stage('tests-on-prod') {
            steps {
                powershell 'git clone https://github.com/mtararujs/course-js-api-framework'

                powershell 'npm install'

                powershell 'npm run greetings greetings_prod'
                
                echo 'Testin on PROD has started..'
            }
        }
    }
}