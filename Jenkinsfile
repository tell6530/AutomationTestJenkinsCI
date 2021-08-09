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
                            sh script:
                            """
                                pwd
                                robot -i RAT -V ${WORKSPACE}/QA/subscription-api-qa/Variable/var_SubscriptionAPI_dev.py ${WORKSPACE}/QA/subscription-api-qa/Testcase/External/Get_company_entitlement_and_subscriptions.robot
                            """
                        }
                    }
                }
            }
        }
    }
}