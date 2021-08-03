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
                    sh "git clone git@github.com:tell6530/DesignPattern.git"
                }
            }
        }
    }
}