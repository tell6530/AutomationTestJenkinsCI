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
                        sh """echo 'susu automation test'"""
                    }
                }
            }
        }
    }
}