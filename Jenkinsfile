pipeline{
    agent any
    stages{

        stage('Pull latest image'){
            steps{
                sh "docker pull gahung206/selenium-docker" //not time consuming
            }
        }

        stage('Start selenium grid'){
            steps{
                sh "docker-compose up --no-color -d hub chrome firefox" //turn off colors in Jenkins
            }
        }

        stage('Run Test'){
            steps{
                sh "docker-compose up search-module book-flight-module" //turn off colors in Jenkins
            }
        }

        stage("Bring selenium grid down"){
            steps {
                sh "docker-compose down"
            }
        }
    }
}