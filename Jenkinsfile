// pipeline {
//   agent {
//     kubernetes {
//           inheritFrom 'dockers'
//         }
//   }

//   stages {
//     // stage ('docker') {
//     //         steps {
//     //             container('ali') {
//     //                 script {
//     //                     sh "docker build . -t test "
//     //                     sh "docker images"
//     //                 }
//     //             }
//     //         }
//     //     }
//       stage ('docker') {
//             steps {
//                 container('jnlp') {
//                     script {
//                         sh "terraform --version"
//                         // sh "helm version"
//                         // sh "kubectl version"
//                     }
//                 }
//             }
//         }
//     stage('Hello world') {
//       agent {
//         kubernetes {
//           inheritFrom 'terraform'
//         }
//       }
//       steps {
//           sh "terraform --version"
//           // sh "kubectl version"
//       }
//     }
//   } 
// }


pipeline {
    agent {
        kubernetes {
            cloud 'kubernetes'
            label 'jenkins-slave'
            defaultContainer 'jnlp'
        }
    }
    stages {
        stage('Build') {
            steps {
                container('busybox') {
                    sh 'helm version'
                    sh 'kubectl version'
                    // sh 'terrform --version'
                }
            }
        }
        // stage('Test') {
        //     steps {
        //         container('jnlp') {
        //             sh 'echo "Running tests inside jnlp container"'
        //         }
        //     }
        // }
    }
}
