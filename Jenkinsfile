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
                            sh 'cp -r ${WORKSPACE}/QA/* /opt/robotframework/tests'
                            sh 'ls /opt/robotframework/tests'
                            sh 'cp -r ${WORKSPACE}/QA/reports/* /opt/robotframework/reports'
                            sh 'ls /opt/robotframework/reports'
                            sh 'robot -i RAT -V /opt/robotframework/tests/subscription-api-qa/Variable/var_SubscriptionAPI_qa.py /opt/robotframework/tests/subscription-api-qa/Testcase/External/Get_company_entitlement_and_subscriptions.robot'
                        }
                    }
                }
            }
        }
    }
}