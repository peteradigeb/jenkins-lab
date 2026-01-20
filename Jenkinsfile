pipeline {
    agent any

    environment {
        APP_ENV = "ci"
    }

    stages {
        stage('Test') {
            steps {
                sh 'echo "Environment: $APP_ENV"'
                sh 'chmod +x app.sh'
                sh './app.sh'
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded'
        }
        failure {
            echo 'Pipeline failed — fix required'
        }
    }
}

