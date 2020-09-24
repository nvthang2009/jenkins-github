pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git credentialsId: 'webhook-2', url: 'https://gitlab.com/thangnv2009/webhook-2.git'
            }
        }
    }
}
