pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh "echo Building frontend"
                sh "cd frontend && npm install && npm run build"
            }
        }
        
    }
}