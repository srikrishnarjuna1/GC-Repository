
pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                checkout scm
            }
        }

        stage('Hello World') {
            steps {
                echo '================================'
                echo 'HELLO WORLD!'
                echo 'Welcome to Jenkins CI/CD'
                echo '================================'
            }
        }

        stage('Check Java') {
            steps {
                bat 'java -version'
            }
        }

        stage('Build') {
            steps {
                echo 'Build completed successfully!'
            }
        }
    }

    post {
        success {
            echo 'Congratulations! Pipeline SUCCESS.'
        }

        failure {
            echo 'Sorry! Pipeline FAILED.'
        }
    }
}
