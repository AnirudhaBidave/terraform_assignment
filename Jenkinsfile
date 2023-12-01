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
                    def tfPlanOutput = sh(script: 'terraform plan -out=tfplan', returnStdout: true).trim()
                        echo "Terraform Plan Output: ${tfPlanOutput}"
                     }
                }
            }
        }

        stage('Apply') {
            steps {
                script{
                    sh 'terraform apply -auto-approve tfplan'
                }
            }
        }
    }
}
