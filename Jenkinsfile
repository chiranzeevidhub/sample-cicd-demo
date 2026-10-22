pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build/Test') {
            steps {
                echo 'Running tests...'
                // e.g. sh 'npm test' or html validation
            }
        }

        stage('Check User') {
            steps {
                echo 'Checking the user running Jenkins...'
                sh 'whoami'
            }
        }

        stage('Deploy') {
            steps {
                sh 'cp -r index.html /var/www/html/'
                // for a whole project:
                // sh 'rsync -av --delete --exclude=".git" --exclude="Jenkinsfile" ./ /var/www/html/'
            }
        }
    }

    post {
        success {
            echo 'Deployed successfully!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}
