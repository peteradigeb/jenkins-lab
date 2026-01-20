pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Code checked out'
            }
        }

        stage('Build') {
            steps {
                echo 'Build stage (nothing to build yet)'
            }
        }

        stage('Test') {
            steps {
                sh './app.sh'
            }
        }
    }
}
