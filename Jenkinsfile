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
        stage('Checkout') {
            steps {
                git branch: 'feature1', url: 'https://github.com/rohithn202/jenkins-terraform-integration.git'
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

        stage('Terraform Init - Base') {
            steps {
                dir('infra/base') {  
                    sh 'terraform init'
                }
            }
        }
        stage('Terraform Apply - Base') {
            steps {
                dir('infra/base') {  
                    sh 'terraform apply --auto-approve'
                }
            }
        }
        stage('Terraform Init - News') {
            steps {
                dir('infra/news') {  
                    sh 'terraform init'
                }
            }
        }
        stage('Terraform Apply - News') {
            steps {
                dir('infra/news') {  
                    sh 'terraform apply --auto-approve'
                }
            }
        }
    }
}
