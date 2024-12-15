pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'eks-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://1D56294697F0928D3E46B155EC687FFA.gr7.ap-south-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                    
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'eks-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://1D56294697F0928D3E46B155EC687FFA.gr7.ap-south-1.eks.amazonaws.com']]) {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}
