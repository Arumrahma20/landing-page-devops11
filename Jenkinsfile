

pipeline {
    agent any

    stages {
        stage('Pull Code') {
            steps {
                git url: 'https://github.com/Arumrahma20/landing-page-devops11.git', branch: 'main'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t landing-page:latest .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f landing-page || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d --name landing-page -p 80:80 -v /home/devops/html:/usr/share/nginx/html landing-page:latest'
            }
        }
    }
}