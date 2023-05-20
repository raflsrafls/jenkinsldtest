pipeline {
    agent any
    
    stages {
        stage('install-pip-deps') {
            steps {
                echo 'Installing PIP has started ...'
                powershell 'git clone https://github.com/mtararujs/python-greetings'
                powershell 'ls python-greetings'
                powershell 'pip install -r python-greetings\\requirements.txt'
            }
        }
        stage('deploy-to-dev') {
            steps {
                powershell 'pm2 start python-greetings/app.py --name greetings-app-dev -p 7001'
                powershell 'pm2 delete greetings-app-dev ; set "errorlevel=0"'
                echo 'Deployment to DEV has started..'
            }
        }
        stage('tests-on-dev') {
            steps {
                powershell 'git clone https://github.com/mtararujs/course-js-api-framework.git'
                powershell 'cd C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\course-js-api-framework\\'
                powershell 'npm install'
                //npm run greetings greetings_dev
                echo 'Testing on DEV has started..'
            }
        }
        stage('deploy-to-staging') {
            steps {
                powershell 'pm2 start python-greetings/app.py --name greetings-app-staging -p 7002'
                powershell 'pm2 delete greetings-app-staging ; set "errorlevel=0"'
                echo 'Deployment to STG has started..'
            }
        }
        stage('tests-on-staging') {
            steps {
                powershell 'cd C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\course-js-api-framework\\'
                powershell 'npm install'
                //npm run greetings greetings_staging
                echo 'Testing on STG has started..'
            }
        }
        stage('deploy-to-preprod') {
            steps {

                powershell 'pm2 start python-greetings/app.py --name greetings-app-preprod -p 7003'
                powershell 'pm2 delete greetings-app-preprod ; set "errorlevel=0"'
                echo 'Deployment to PRD has started..'
            }
        }
        stage('tests-on-preprod') {
            steps {
                powershell 'cd C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\course-js-api-framework\\'
                powershell 'npm install'
                //npm run greetings greetings_preprod
                echo 'Testing on PRD has started..'
            }
        }
        stage('deploy-to-prod') {
            steps {

                powershell 'pm2 start python-greetings/app.py --name greetings-app-prod -p 7004'
                powershell 'pm2 delete greetings-app-prod ; set "errorlevel=0"'
                echo 'Deployment to PROD has started..'
            }
        }
        stage('tests-on-prod') {
            steps {

                powershell 'cd C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\course-js-api-framework\\'
                powershell 'npm install'
                //npm run greetings greetings_prod
                echo 'Testing on PROD has started..'
            }
        }
    }
}
