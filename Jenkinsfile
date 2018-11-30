pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                 sh 'make clean'
                 sh 'make build'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh 'make deploy'
            }
        }
    }
}
