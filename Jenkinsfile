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
        yaml '''
          apiVersion: v1
          kind: Pod
          spec:
            containers:
            - name: docker
              image: docker:24.0.7
              command:
              - cat
              tty: true
              volumeMounts:
                - mountPath: /var/run/docker.sock
                  name: docker-sock
            volumes:
            - name: docker-sock
              hostPath:
                path: /var/run/docker.sock    
          '''
      }
    }
    stages {
      stage('Build/Push Image') {
       steps{
        container('docker') {
        script {
         def version = readFile('VERSION')
         patch = version.trim()
         patch = patch + ".$BUILD_NUMBER"
         
         dockerImage = docker.build registry_dev + ":$patch" , "."
        //  docker.withRegistry( 'https://dxb.ocir.io', 'reg-logins' ) { 
        //               dockerImage.push(patch)
        //          }
        //  }
        }
      }
        // stage('Build') {
        //     agent {
        //         kubernetes {
        //           inheritFrom 'jenkins-slave'
        //         }
        //       }
        //     steps {
        //         container('helm') {
        //             sh 'helm version'
        //             sh 'kubectl version'
        //         }
        //     }
        // }
       }
    }
}
