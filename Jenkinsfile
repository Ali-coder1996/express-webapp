pipeline {
  agent none
  environment {
        KUBECONFIG = ''
    }
  stages {
    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "hellodocker.yml", kubeconfigId: "KUBE")
        }
      }
    }
  }
} 
