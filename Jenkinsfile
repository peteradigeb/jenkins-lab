pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-docker-demo .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run --rm jenkins-docker-demo'
            }
        }
    }
}
