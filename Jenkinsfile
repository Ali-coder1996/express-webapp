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
                - name: maven
                  image: maven:3.6.0-jdk-11-slim
                  command: ["cat"]
                  tty: true
                  volumeMounts:
                  - name: repository
                    mountPath: /root/.m2/repository
                - name: docker
                  image: docker:18.09.3
                  command: ["cat"]
                  tty: true
                  volumeMounts:
                  - name: docker-sock
                    mountPath: /var/run/docker.sock
                volumes:
                - name: repository
                  persistentVolumeClaim:
                    claimName: repository
                - name: docker-sock
                  hostPath:
                    path: /var/run/docker.sock
              """
        }
    }

  stages {

    stage ('docker') {
            steps {
                container('docker') {
                    script {
                        sh "docker build . -t test "
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


