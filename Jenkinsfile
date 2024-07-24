
                pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeConfig(caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', restrictKubeConfigAccess: false, serverUrl: 'https://7D1B83D551C74FE78AAB33CA9A86C10D.gr7.ap-south-1.eks.amazonaws.com') {

                  sh " kubectl apply -f deployment-service.yml "
                  }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeConfig(caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', restrictKubeConfigAccess: false, serverUrl: 'https://7D1B83D551C74FE78AAB33CA9A86C10D.gr7.ap-south-1.eks.amazonaws.com') {

                  sh " kubectl get svc -n webapps"
                  }
            }
            }
        
    }
}
                
                
         
