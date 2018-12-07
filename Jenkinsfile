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
                sh 'make reset'
                /*sh 'make deploy'*/
            }
        }
    }
}
