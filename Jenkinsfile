pipeline {
  agent {
    kubernetes {
          inheritFrom 'dockers'
        }
  }

  stages {
    // stage ('docker') {
    //         steps {
    //             container('ali') {
    //                 script {
    //                     sh "docker build . -t test "
    //                     sh "docker images"
    //                 }
    //             }
    //         }
    //     }
      stage ('docker') {
            steps {
                container('jnlp') {
                    script {
                        sh "terraform --version"
                        // sh "helm version"
                        // sh "kubectl version"
                    }
                }
            }
        }
    stage('Hello world') {
      agent {
        kubernetes {
          inheritFrom 'terraform'
        }
      }
      steps {
          sh "terraform --version"
          // sh "kubectl version"
      }
    }
  } 
}


