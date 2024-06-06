pipeline {
  agent {
        kubernetes {
            label 'build-service'
            defaultContainer 'jnlp'
            yaml """
              apiVersion: v1
              kind: Pod
              metadata:
                labels:
                  job: build-service
              spec:
                containers:
                - name: jnlp
                  image: docker:24.0.7
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
    stage ('docker') {
            steps {
                container('jnlp') {
                    script {
                        sh "docker build . -t test "
                        sh "docker images"
                    }
                }
            }
        }
    // stage('Hello world') {
    //   agent {
    //     kubernetes {
    //       inheritFrom 'docker'
    //     }
    //   }
    //   steps {
    //       sh "docker version"
    //       sh "slepp 1000"
    //   }
    // }
  } 
}


