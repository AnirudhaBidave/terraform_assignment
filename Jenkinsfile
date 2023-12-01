pipeline {
    agent any

environment {
        AWS_REGION = 'us-west-1'
    }
    
    stages {
        stage('Init') {
            steps {
                 
                sh 'terraform init'
            }
        }

        stage('Plan') {
            steps {
                withAWS(region: AWS_REGION, credentials: 'AWS_KEYS') {
                sh 'terraform plan'
            }
            }
        }

        stage('Apply') {
            steps {
                withAWS(region: AWS_REGION, credentials: 'AWS_KEYS') {
                sh 'terraform apply -auto-approve'
            }
        }
    }
}
