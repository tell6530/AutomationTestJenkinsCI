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
                            sh 'cp /c/Users/ext_stevensu/TrendMicro/QA /opt/robotframework/tests'
                            sh 'cp /c/Users/ext_stevensu/TrendMicro/QA/reports /opt/robotframework/reports'
                        }
                    }
                }
            }
        }
    }
}