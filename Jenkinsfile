pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                    // Install the desired Go version
                def root = tool name: 'Go 1.8', type: 'go'

                // Export environment variables pointing to the directory where Go was installed
                withEnv(["GOROOT=${root}", "PATH+GO=${root}/bin"]) {
                    sh 'go version'
                }
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
