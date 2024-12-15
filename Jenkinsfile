pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
               sh 'docker build -t harini502/shippingservice:v1 .'
            }
        }
        stage("push") {
            steps {
               script{
                   withDockerRegistry(credentialsId: 'docker-cred') {
                        sh 'docker push harini502/shippingservice:v1'
                    }
               }
            }
        }
    }
}
