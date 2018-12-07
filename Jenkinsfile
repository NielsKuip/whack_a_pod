pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
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
                sh 'kubectl delete deployment admin-deployment'
                sh 'kubectl delete deployment api-deployment'
                sh 'kubectl delete deployment game-deployment'
                sh 'make deploy'
            }
        }
    }
}
