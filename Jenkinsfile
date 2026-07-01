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
    }
}