pipeline {
    agent any
    tools {
        terraform 'Terraform'
    }
    environment {
        AWS_ACCESS_KEY_ID     = credentials('AWS_Accesskey')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_Secretaccesskey')
    }

    stages {
        stage('checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/rohithn202/jenkins-terraform-integration.git'
            }
        }
        stage('terraform init') {
            steps {
                dir('infra/backend-support') {  
                    sh 'terraform init'
                }
            }
        }
        stage('Terraform apply') {
            steps {
                dir('infra/backend-support') {  
                    sh 'terraform apply --auto-approve'
                }
            }
        }
    }
}
