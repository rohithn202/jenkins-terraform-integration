pipeline {
    agent any
    tools {
        terraform 'terraform'
    stages {
        stage('checkout'){
            steps {
                git branch: 'master', url: 'https://github.com/rohithn202/jenkins-terraform-integration.git'
            }
        }
        stage('terraform init') {
            steps {
                sh 'terraform init'
            }
        }
        stage('Terraform apply') {
            steps {
                sh 'terraform apply --auto-approve'
            }
        }
        
    }
}
