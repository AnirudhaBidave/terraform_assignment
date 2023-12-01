pipeline {
    agent any

environment {
        AWS_REGION = 'us-west-1'
        access_key = "AKIAVQAPERWSSK6QQ5DI"
        secret_key = "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"
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
                     sh 'terraform plan'
                }
            }
        }

        stage('Apply') {
            steps {
                script{
                    sh 'terraform apply -auto-approve'
                }
            }
        }
    }
}
