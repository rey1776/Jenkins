pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh "echo Building frontend"
                sh "cd frontend && npm install && npm run build"
            }
        }
        STAGE('Deploy Frontend'){
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
        
    }
}