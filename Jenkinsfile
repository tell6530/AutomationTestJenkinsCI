pipeline {
    agent any
    environment {
        QA_Workspace = './QA'
    }
    stages {
        stage('build') {
            steps {
                echo 'susu build application'
                sh "pwd"
            }
        }
        stage('git clone') {
            steps {
                script {
                    sh "git clone git@adc.github.trendmicro.com:ext-stevensu/subscription-api-qa.git"
                }
            }
        }
    }
}