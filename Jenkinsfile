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
                sh 'kubectl set image deployment.v1.apps/api-deployment image=gcr.io/kubeshow-224810/api --record'
                sh 'kubectl set image deployment.v1.apps/game-deployment image=gcr.io/kubeshow-224810/game --record'
                sh 'kubectl set image deployment.v1.apps/admin-deployment image=gcr.io/kubeshow-224810/admin --record'
            }
        }
    }
}
