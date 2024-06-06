pipeline {
  agent none

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
                container('vm') {
                    script {
                        sh "helm version"
                        sh "kubectl version"
                    }
                }
            }
        }
    stage('Hello world') {
      agent {
        kubernetes {
          inheritFrom 'vm'
        }
      }
      steps {
          sh "helm version"
          sh "kubectl version"
      }
    }
  } 
}


