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
