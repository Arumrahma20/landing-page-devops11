pipeline {
    agent any

    environment {
        IMAGE_NAME = "landing-page"
        CONTAINER_NAME = "landing-page"
        PORT = "8081"
    }

    stages {
        stage('Checkout Code') {
            steps {
                git url: 'https://github.com/Arumrahma20/landing-page-devops11.git', branch: 'main'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh "docker build --no-cache -t $IMAGE_NAME:latest ."
            }
        }

        stage('Stop & Remove Old Container') {
            steps {
                sh '''
                    echo "🧹 Membersihkan container dengan nama atau port konflik..."

                    # Stop & remove by container name
                    docker rm -f landing-page || true

                    # Check port 8081 in use by any container
                    USED=$(docker ps --format "{{.ID}} {{.Ports}}" | grep 8081 | awk '{print $1}')
                    if [ ! -z "$USED" ]; then
                        echo "⚠️ Port 8081 dipakai container ID: $USED. Menghapus..."
                        docker rm -f $USED || true
                    fi
                '''
            }
        }

        stage('Run New Container') {
            steps {
                sh '''
                    echo "🚀 Menjalankan container baru di port 8081..."
                    docker run -d --name landing-page -p 8081:80 landing-page:latest
                '''
            }
        }
    }
}
