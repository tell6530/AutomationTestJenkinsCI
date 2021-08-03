pipeline {
    agent any
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
                    sh 'ssh-keyscan adc.github.trendmicro.com >> ~/.ssh/known_hosts'
                    sh "git clone git@adc.github.trendmicro.com:ext-stevensu/subscription-api-qa.git"
                    sh 'docker create `
-v $env:\:/opt/robotframework/tests:Z `
-v $env:\reports\:/opt/robotframework/reports:Z `
--name robotframework_data robotframework:latest'
                    sh 'docker run --rm `
--volumes-from robotframework_data `
-e ROBOT_OPTIONS="-t http200-Create* -V ./subscription-api-qa/Variable/var_SubscriptionAPI_qa.py" `
robotframework:latest'
                }
            }
        }
    }
}