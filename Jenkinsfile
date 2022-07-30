pipeline{
    agent any
    stages{
        stage('Run Test'){
            sh "docker-compose up"
        }

        stage("Bring selenium grid down"){
            sh "docker-compose down"
        }

    }
}