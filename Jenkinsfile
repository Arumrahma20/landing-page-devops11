pipeline {
    agent any

    stages {
        stage('Pull Source Code') {
            steps {
                git branch: 'main', url: 'https://github.com/devinovitasari/landing-page-devops.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t landing-page:prod .'
            }
        }

        stage('Stop & Remove Old Container') {
            steps {
                sh '''
                    docker stop landing-page || true
                    docker rm landing-page || true
                '''
            }
        }

        stage('Deploy Container') {
            steps {
                sh 'docker run -d -p 80:80 --name landing-page landing-page:prod'
            }
        }
    }
}
