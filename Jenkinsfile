pipeline {
    agent any

    stages {
        stage('git-clone') {
            steps {
                git 'https://github.com/navaneednavi/s3-static-website.git'
            }
        }
        stage('Terraform initialization') {
            steps {
                sh 'sudo terraform init'
            }
        }
        stage('Terraform apply') {
            steps {
                sh 'sudo terraform apply --auto-approve'
            }
        }
        stage('Cloning the website') {
            steps {
                git branch: 'main', url: 'https://github.com/mohammedashiqu/anglular-project.git'
            }
        }
        stage('Copy website to s3') {
            steps {
                sh 'sudo aws s3 cp /var/lib/jenkins/workspace/pro22/ s3://jekiasdfghjklasdfghgfdnavii --recursive'
            }
        }
    }
}
