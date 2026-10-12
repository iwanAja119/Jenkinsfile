pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Mengambil kode terbaru dari GitHub tes tes 123...'
            }
        }
        stage('Build') {
            steps {
                echo 'Mengompilasi / menyiapkan aplikasi...'
            }
        }
        stage('Test') {
            steps {
                echo 'Menjalankan unit testing otomatis...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Mendeploy aplikasi ke server target...'
            }
        }
    }
}
