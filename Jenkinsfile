pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            agent { label 'docker-node' }
            steps {
                git branch: 'main', url: 'https://github.com/vikasvarmadunna/saleor-dashboard.git'
            }
        }
        stage('docker image build') {
            agent { label 'docker-node' }
            steps {
                sh 'docker image build -t ravi:DEV .'
            }
        }
        stage('push image to registry') {
            agent { label 'docker-node' }
            steps {
                sh 'docker push ravi:DEV'
            }
        }
        stage('create terraform infrastructre') {
            agent { label 'terraform-node' }
            steps {
                git url: 'git clone https://github.com/hashicorp/learn-terraform-provision-eks-cluster'
                sh 'terraform init && terraform apply -auto-approve'
            }
        }
    }
}
