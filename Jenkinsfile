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
                            docker create \
                            -v C:/Users/ext_stevensu/TrendMicro/QA/:/opt/robotframework/tests:Z \
                            -v C:/Users/ext_stevensu/TrendMicro/QA/reports/:/opt/robotframework/reports:Z \
                            --name robotframework_data tell6530/robotframework:latest
                            docker run --rm \
                            --volumes-from robotframework_data \
                            -e ROBOT_OPTIONS="-t http200-Create* -V ./subscription-api-qa/Variable/var_SubscriptionAPI_qa.py" \
                            tell6530/robotframework:latest"""
                    }
                }
            }
        }
    }
}