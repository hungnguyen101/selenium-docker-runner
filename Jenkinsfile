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
                sh "docker-compose up search-module-firefox  book-flight-module-chrome" //turn off colors in Jenkins
            }
        }
    }
    //archive test result
    post{
        always{
            archiveArtifacts artifacts: 'output/'
            sh "docker-compose down"
        }
    }
}