pipeline{
    agent{
        label "mvn"
    }
    stages{
        stage('vcs'){
            steps{
                git branch: 'main', url: 'https://github.com/WorkshopsByKhaja/saleor-dashboard.git'
            }
        }
        stage('docker image build'){
            steps{
                sh 'docker image build -t shaikkhajaibrahim/saleor-dashboar:DEV .'
            }
        }
        stage('push image to registry'){
            steps{
                sh 'docker image push vikasindian/saleor-dashboard:DEV'
            }
        }
    }
}
