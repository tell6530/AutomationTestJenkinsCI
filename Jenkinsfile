pipeline {
    agent any
    environment {
        QA_PROJECT_NAME = "subscription-api-qa"
        QA_PROJECT_AUTOMATIONTEST_VARIABLE = "var_SubscriptionAPI_dev"
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
                    build job: 'Automation Test Single Job', parameters: [string(name: 'QA_PROJECT_NAME',  value: "${QA_PROJECT_NAME}"), string(name: 'QA_PROJECT_AUTOMATIONTEST_VARIABLE',  value: "${QA_PROJECT_AUTOMATIONTEST_VARIABLE}")]
                }
            }
        }
    }
}