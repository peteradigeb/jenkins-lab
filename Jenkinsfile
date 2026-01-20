pipeline {
    agent any

    environment {
        DEV_TAG = "jenkins-demo:dev"
        PROD_TAG = "jenkins-demo:prod"
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building Docker image for Dev'
                sh 'docker build -t $DEV_TAG .'
            }
        }

        stage('Test/Dev') {
            steps {
                echo 'Running Dev container'
                sh 'docker run --rm $DEV_TAG'
            }
        }

        stage('Prod') {
            steps {
                echo 'Tagging and pushing Docker image to PROD'
                sh 'docker tag $DEV_TAG $PROD_TAG'
                # Optional: push to DockerHub (requires credentials)
                # sh 'docker push $PROD_TAG'
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded: Dev → Prod complete'
        }
        failure {
            echo 'Pipeline failed: investigate logs'
        }
    }
}
