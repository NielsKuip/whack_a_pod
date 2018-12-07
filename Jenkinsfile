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
                sh 'kubectl rolling-update admin-deployment --image=gcr.io/kubeshow-224810/admin'
                sh 'kubectl rolling-update api-deployment --image=gcr.io/kubeshow-224810/api'
                sh 'kubectl rolling-update game-deployment --image=gcr.io/kubeshow-224810/game'
            }
        }
    }
}
