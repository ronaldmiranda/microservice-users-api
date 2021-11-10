node {
    checkout scm
    stage "feching helm repo"
        sh "helm dependency update ./helm"
    stage('Deploy to cluster') {
        sh '''
            helm upgrade --install microservice-users-api ./helm \
                         --set microservice-deploys.container.namespace=microservice-ns \
                         --kubeconfig /home/ubuntu/.kube/config
           '''
    }
}
