pipeline {
    agent any
    stages {
        stage("Setup Selenium Grid"){
            steps{
                sh "docker-compose up -d seleniumhub chromenode firefoxnode"
                // It is required to setup the Grid related services separately as after executing the tests the Job still keeps on Running and waiting for more requests
                // -d is used to detach the process after setting up Grid
                // if not invoked grid separately than it will result in a never ending Jenkins Job
            }
        }
        stage("Run Automated Tests"){
            steps{
                sh "docker-compose up automation_service"
            }
        }
    }
    post{
        always{
            archiveArtifacts artifacts: 'output/**'
            sh "docker-compose down"
        }
    }
}