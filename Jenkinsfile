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
                sh 'kubectl apply -f "https://raw.githubusercontent.com/NielsKuip/whack_a_pod/master/apps/admin/kubernetes/admin-deployment.yaml"'
                sh 'kubectl apply -f "https://raw.githubusercontent.com/NielsKuip/whack_a_pod/master/apps/game/kubernetes/game-deployment.yaml"'
                sh 'kubectl apply -f "https://raw.githubusercontent.com/NielsKuip/whack_a_pod/master/apps/api/kubernetes/api-deployment.yaml"'

            }
        }
    }
}
