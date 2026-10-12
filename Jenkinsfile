pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Mengambil kode terbaru dari GitHub tes lagi run ke 02...'
            }
        }
        stage('Build') {
            steps {
                echo 'Mengompilasi / menyiapkan aplikasi tes tes run ke 02 setelah salah tadi wkwk :>...'
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
