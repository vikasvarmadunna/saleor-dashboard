pipeline{
    agent{
        label "docker-node"
    } 
    triggers {
        pollSCM('40 3 * * *')
    }
    stages{
        stage('vcs'){
            steps{
                git branch: 'main', url: 'https://github.com/vikasvarmadunna/saleor-dashboard.git'
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
