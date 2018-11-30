pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                 sh 'cd /infrastructure'
                 sh 'make build'
                 sh 'cd ..' 
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
