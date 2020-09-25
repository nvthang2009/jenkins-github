pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/nvthang2009/jenkins-github.git'
            }
        }
        stage('build') {
            steps {
                withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
                    sh label: '', script: 'docker build -t thangnv/golang-test:v1 .'
                    sh label: '', script: 'docker push thangnv/golang-test:v1'
                }
>>>>>>> 4e0a8b2e85e7c9fedff60d4b816c07eb0c88b90f
            }
        }
    }
}
