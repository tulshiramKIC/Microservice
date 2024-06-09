pipeline { 
    agent any

    stages {
        stage('Deploy') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: ' K8S-CLUSTER', contextName: '', credentialsId: '', namespace: 'webapps', serverUrl: 'https://DEB07F0013862353B5DF8841D13EEACC.gr7.ap-south-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                }
            }
        }
        
        stage('Status') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: ' K8S-CLUSTER', contextName: '', credentialsId: '', namespace: 'webapps', serverUrl: 'https://DEB07F0013862353B5DF8841D13EEACC.gr7.ap-south-1.eks.amazonaws.com']]) {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}
