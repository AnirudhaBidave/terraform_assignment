pipeline {
    agent any

environment {
        AWS_REGION = 'us-west-1'
    }
    
    stages {
        stage('Init') {
            steps {
                script{
                    sh 'terraform init'
                }
            }
        }

        stage('Plan') {
            steps {
                script{
                    withAWS(region: AWS_REGION, credentials: 'AWS_KEYS') {
                    sh 'terraform plan'
                    }
                }
            }
        }

        stage('Apply') {
            steps {
                script{
                    withAWS(region: AWS_REGION, credentials: 'AWS_KEYS') {
                    sh 'terraform apply -auto-approve'
                    }
                }
            }
        }
    }
}
