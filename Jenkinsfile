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
                sh 'docker image build -t vikas/saleor-dashboar:DEV .'
            }
        }
    }
}
