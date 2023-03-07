pipeline {
    agent any

    stages {
        stage('git-clone') {
            steps {
                git 'https://github.com/navaneednavi/s3-static-website.git'
            }
        }
        stage('init') {
            steps {
                sh 'sudo terraform init'
            }
        }
        stage('apply') {
            steps {
                sh 'sudo terraform apply --auto-approve'
            }
        }
        stage('git-clone-2') {
            steps {
                git branch: 'main', url: 'https://github.com/mohammedashiqu/anglular-project.git'
            }
        }
        stage('copy') {
            steps {
                sh 'sudo aws s3 cp /var/lib/jenkins/workspace/pro22/ s3://jekiasdfghjklasdfghgfdnavii --recursive'
            }
        }
    }
}
