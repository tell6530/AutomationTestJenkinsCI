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
                        def image_sdk = docker.image('tell6530/robotframework:latest')
                        image_sdk.pull()
                        image_sdk.inside(){
                            sh 'pwd'
                            sh 'cp -r ${WORKSPACE}/QA /opt/robotframework/tests'
                            sh 'ls /opt/robotframework/tests/QA'
                            sh 'cp -r ${WORKSPACE}/QA/reports /opt/robotframework/reports'
                            sh 'ls /opt/robotframework/reports/reports'
                        }
                    }
                }
            }
        }
    }
}