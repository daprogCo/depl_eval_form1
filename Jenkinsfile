pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *') // Vérifie les modifications toutes les 5 minutes
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'master', url: 'https://github.com/daprogCo/depl_eval_form1.git'
            }
        }
        stage('Build Docker Images') {
            steps {
                script {
                    docker.build('yourimage:latest')
                }
            }
        }
        stage('Run Containers') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}