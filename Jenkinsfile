pipeline {
    agent any
    environment {
        PROJECT_NAME = "Automation Test"
    }
    stages {
        stage('build') {
            steps {
                echo 'susu build application'
            }
        }
        stage('automation test') {
            steps {
                catchError {
                    build job: 'Automation Test Single Job', parameters: [string(name: 'PROJECT_NAME',  value: "${PROJECT_NAME}")]
                }
            }
        }
    }
}