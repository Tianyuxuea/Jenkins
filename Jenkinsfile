pipeline {
    agent any

    environment {
        DIRECTORY_PATH = '/home/zhihai/myapp'          // 你可以改成任意路径
        TESTING_ENVIRONMENT = 'TestEnv'
        PRODUCTION_ENVIRONMENT = 'ZhihaiYang'          // 用你的名字
    }

    stages {
        stage('Build') {
            steps {
                echo "Fetch the source code from the directory path specified by the environment variable: ${env.DIRECTORY_PATH}"
                echo "Compile the code and generate any necessary artefacts"
            }
        }

        stage('Test') {
            steps {
                echo "Unit tests"
                echo "Integration tests"
            }
        }

        stage('Code Quality Check') {
            steps {
                echo "Check the quality of the code"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploy the application to a testing environment specified by the environment variable: ${env.TESTING_ENVIRONMENT}"
            }
        }

        stage('Approval') {
            steps {
                echo "Waiting for manual approval..."
                sleep time: 10, unit: 'SECONDS'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying the application to the production environment: ${env.PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}
