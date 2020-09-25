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
                    sh label: '', script: 'docker build -t thangnv/golang-test:v2 .'
                    sh label: '', script: 'docker push thangnv/golang-test:v2'
                }
            }
        }
        stage('ssh'){
            steps {
                sshagent(['keybuild']) {
                    sh 'ssh -o StrictHostKeyChecking=no -l root 10.120.102.20 touch test.txt'
                }
            }
        }
    }
}
