
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Source code checked out'
            }
        }

        stage('Execute Shell Script') {
            steps {
                bat '''
                    "C:\\Program Files\\Git\\bin\\bash.exe" app.sh
                '''
            }
        }
    }

    post {
        success {
            echo 'Shell script executed successfully!'
        }
        failure {
            echo 'Shell script execution failed!'
        }
    }
}
