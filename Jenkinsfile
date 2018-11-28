pipeline {
    agent any
    ws("${JENKINS_HOME}/jobs/${JOB_NAME}/builds/${BUILD_ID}/") {
            withEnv(["GOPATH=${JENKINS_HOME}/jobs/${JOB_NAME}/builds/${BUILD_ID}"]) {
                env.PATH="${GOPATH}/bin:$PATH"
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
                            sh 'make deploy'
                        }
                    }
                }
            }
    }
 }
