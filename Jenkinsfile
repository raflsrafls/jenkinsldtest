pipeline {
    agent any
    
    stages {
        stage('install-pip-deps') {
            steps {
                echo 'Installing PIP has started ...'
                bat 'git clone https://github.com/mtararujs/python-greetings'
                bat 'ls python-greetings'
                bat 'pip install -r python-greetings\\requirements.txt'
            }
        }
        stage('deploy-to-dev') {
            steps {
                echo 'Deployment to DEV has started..'
                bat 'pm2 start python-greetings/app.py --name greetings-app-dev -p 7001'
                bat 'pm2 delete greetings-app-dev ; set "errorlevel=0"'
            }
        }
        stage('tests-on-dev') {
            steps {
                echo 'Testing on DEV has started..'
                bat 'git clone https://github.com/mtararujs/course-js-api-framework.git'
                bat 'cd C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\course-js-api-framework\\'
                bat 'npm install'
                //npm run greetings greetings_dev
            }
        }
        stage('deploy-to-staging') {
            steps {
                echo 'Deployment to STG has started..'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-staging -p 7002'
                powershell 'pm2 delete greetings-app-staging ; set "errorlevel=0"'
            }
        }
        stage('tests-on-staging') {
            steps {
                echo 'Testing on STG has started..'
                powershell 'cd C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\course-js-api-framework\\'
                powershell 'npm install'
                //npm run greetings greetings_staging
            }
        }
        stage('deploy-to-preprod') {
            steps {
                echo 'Deployment to PRD has started..'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-preprod -p 7003'
                powershell 'pm2 delete greetings-app-preprod ; set "errorlevel=0"'
            }
        }
        stage('tests-on-preprod') {
            steps {
                echo 'Testing on PRD has started..'
                powershell 'cd C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\course-js-api-framework\\'
                powershell 'npm install'
                //npm run greetings greetings_preprod
            }
        }
        stage('deploy-to-prod') {
            steps {
                echo 'Deployment to PROD has started..'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-prod -p 7004'
                powershell 'pm2 delete greetings-app-prod ; set "errorlevel=0"'
            }
        }
        stage('tests-on-prod') {
            steps {
                echo 'Testing on PROD has started..'
                powershell 'cd C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\course-js-api-framework\\'
                powershell 'npm install'
                //npm run greetings greetings_prod
            }
        }
    }
}
