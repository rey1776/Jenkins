pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh "echo Building frontend"
                sh "cd frontend && npm install && npm run build"
            }
        }
        stage('Deploy Frontend'){
            steps {
                script{ 
                    try{
                        withAWS(region:'us-east-1', credentials: 'AWS_CREDENTIALS'){
                            sh "aws s3 sync frontend/dist s3://team-6-frontend-jenkins"
                        }
                    }catch(Exception e){
                        echo "${e}"
                        throw e
                    }
                }
            }
        }
        stage('Building backend'){
            steps{
                sh "cd demo && mvn clean install && ls target/"
            }
        }
        ll
    }
}