pipeline {
  agent {
        kubernetes {
            label 'build-service'
            defaultContainer 'ali'
            yaml """
              apiVersion: v1
              kind: Pod
              metadata:
                labels:
                  job: build-service
              spec:
                containers:
                - name: ali
                  image: alialhjouj/jenkins:v3
                  command: ["cat"]
                  tty: true
                  volumeMounts:
                  - name: docker-sock
                    mountPath: /var/run/docker.sock
                volumes:
                - name: docker-sock
                  hostPath:
                    path: /var/run/docker.sock
              """
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
                container('ali') {
                    script {
                        sh "helm version"
                        sh "kubectl version"
                    }
                }
            }
        }
    // stage('Hello world') {
    //   agent {
    //     kubernetes {
    //       inheritFrom 'ali'
    //     }
    //   }
    //   steps {
    //       sh "helm version"
    //       sh "kubectl bersion"
    //   }
    // }
  } 
}


