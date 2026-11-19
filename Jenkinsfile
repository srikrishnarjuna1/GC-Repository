
pipeline {
    agent any

    environment {
        APP_NAME = 'hello-world-jenkins-cicd'
        APP_VERSION = '1.0'
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Fetching source code from GitHub'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Starting application build'

                sh '''
                    chmod +x app.sh
                    bash -n app.sh
                    echo "Build completed successfully"
                '''
            }
        }

        stage('Test') {
            steps {
                echo 'Starting application testing'

                sh '''
                    grep -q "HELLO WORLD APPLICATION" app.sh
                    grep -q "Welcome to Jenkins CI/CD Project" app.sh
                    echo "All tests passed"
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application'

                sh '''
                    mkdir -p deployment
                    cp app.sh deployment/
                    chmod +x deployment/app.sh

                    echo "Deployment completed"
                '''
            }
        }

        stage('Run Application') {
            steps {
                echo 'Running deployed application'

                sh '''
                    ./deployment/app.sh
                '''
            }
        }
    }

    post {
        success {
            echo 'SUCCESS: Jenkins CI/CD completed!'
        }

        failure {
            echo 'FAILURE: Jenkins CI/CD failed!'
        }

        always {
            echo 'Pipeline execution completed'
        }
    }
}
