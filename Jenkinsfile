pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/<username>/sample-cicd-demo.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Build Successful'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing Successful'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                sudo cp index.html /var/www/html/index.html
                '''
            }
        }
    }
}
