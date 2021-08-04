pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'susu build application'
            }
        }
        stage('automation test') {
            steps {
                catchError {
                    script {
                        sh """mkdir -p ./QA/reports
                            cd ./QA/
                            ssh-keyscan adc.github.trendmicro.com >> ~/.ssh/known_hosts
                            git clone git@adc.github.trendmicro.com:ext-stevensu/subscription-api-qa.git
                            docker ps -a"""
                    }
                }
            }
        }
    }
}