pipeline {
    agent any
    tools {
        terraform 'Terraform'
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
