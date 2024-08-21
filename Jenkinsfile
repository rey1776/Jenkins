pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh "echo Building frontend"
                sh "cd frontend && npm install && npm run dev"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing started...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying now!'
            }
        }
    }
}