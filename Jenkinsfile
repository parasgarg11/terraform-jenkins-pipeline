pipeline {
    agent any
    
    tools {
        terraform 'terraform'
    }
    stages {
        stage ("checkout from GIT") {
            steps {
                git branch: 'main', credentialsId: 'github_for_terraform', url: 'https://github.com/parasgarg11/terraform-jenkins-pipeline.git'
            }
        }
        stage ("terraform init") {
            steps {
                sh 'terraform init'
            }
        }
        stage ("terraform fmt") {
            steps {
                sh 'terraform fmt'
            }
        }
        stage ("terraform validate") {
            steps {
                sh 'terraform validate'
            }
        }
        stage ("terrafrom plan") {
            steps {
                sh 'terraform plan -out myplan'
            }
        }
        stage ("terraform apply") {
            steps {
                sh 'terraform apply --auto-approve myplan'
            }
        }
    }
}
