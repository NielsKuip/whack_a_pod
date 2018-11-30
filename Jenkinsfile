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
                sh 'kubectl set image deployment.v1.apps/admin-deployment admin=gcr.io/kube-224111/admin:latest --record'
                sh 'kubectl set image deployment.v1.apps/api-deployment api=gcr.io/kube-224111/api:latest --record'
                sh 'kubectl set image deployment.v1.apps/game-deployment game=gcr.io/kube-224111/game:latest --record'
                /*sh 'make deploy'*/
            }
        }
    }
}
