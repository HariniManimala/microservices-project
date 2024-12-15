pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
               sh 'docker build -t harini502/recommendationservice:v1 .'
            }
        }
        stage("push") {
            steps {
               script{
                   withDockerRegistry(credentialsId: 'docker-cred') {
                        sh 'docker push harini502/recommendationservice:v1'
                    }
               }
            }
        }
    }
}
