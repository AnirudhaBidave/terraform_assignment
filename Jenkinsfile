pipeline {
    agent any

environment {
        AWS_REGION = 'us-west-1'
    }
    
    stages {
        stage('Init') {
            steps {
                script{
                     withAWS(region: AWS_REGION, credentials: 'AWS') {
                    sh 'terraform init'
                     }
                }
            }
        }

        stage('Plan') {
            steps {
                script{
                     withAWS(region: AWS_REGION, credentials: 'AWS') {
                    sh 'terraform plan'
                     }
                }
            }
        }

        stage('Apply') {
            steps {
                script{
                     withAWS(region: AWS_REGION, credentials: 'AWS') {
                    sh 'terraform apply -auto-approve'
                    }
                }
            }
        }
    }
}
