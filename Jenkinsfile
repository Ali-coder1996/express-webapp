pipeline {
  agent none
  environment {
        KUBECONFIG = ''
    }
  stages {
    // stage('k9s') {
    //   agent {
    //     kubernetes {
    //       inheritFrom 'vm'
    //     }
    //   }
    //   steps {
    //         withCredentials([file(credentialsId: 'KUBE', variable: 'KUBECONFIG')]) {
    //             script {
    //                 // Now the KUBECONFIG environment variable points to the temporary file location
    //                 echo "Using kubeconfig file at: ${env.KUBECONFIG}"

    //                 // You can now use kubectl commands
    //                 sh 'kubectl get ns'
    //             }
    //         }
    //         sh "echo hi"
    //       }
    // }
    stage('terraform') {
      agent {
        kubernetes {
          inheritFrom 'helm'
        }
      }
      steps {
          sh "helm version"
      }
    }
  } 
}
