pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                echo 'Mengambil kode terbaru dari GitHub...'
                checkout scm
            }
        }
        stage('Build Docker Image') {
            steps {
                echo 'Mulai memasak image Docker...'
                sh 'docker build -t web-automasi:latest .'
            }
        }
        stage('Deploy Container') {
            steps {
                echo 'Menjalankan kontainer aplikasi web...'
                // Menghentikan dan menghapus kontainer lama jika ada agar tidak bentrok
                sh 'docker rm -f proyek-web-automasi || true'
                // Menjalankan kontainer baru di port 8085
                sh 'docker run -d -p 8085:80 --name proyek-web-automasi web-automasi:latest'
            }
        }
    }
}