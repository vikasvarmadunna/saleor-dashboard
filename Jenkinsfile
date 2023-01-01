pipeline{
    agent{
        label "jenkins-node"
    }
    stages{
        stage('vcs'){
            steps{
                git branch: 'main', url: 'https://github.com/WorkshopsByKhaja/saleor-dashboard.git'
            }
        }
        stage('docker image build'){
            steps{
                sh 'docker image build -t vikasindian/saleor-dashboar:DEV .'
            }
        }
        stage('push image to registry'){
            steps{
                sh 'docker image push vikasindian/saleor-dashboar:DEV'
            }
        }
    }
}
