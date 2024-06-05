pipeline {
  agent none

  stages {
    stage('Hello world') {
      agent {
        kubernetes {
          inheritFrom 'docker'
        }
      }
      steps {
          sh "sudo docker run helloworld"
          sh "whoami && pwd"
          sh "docker version"
          sh "systemctl start docker"
          sh "docker run helloworld"
      }
    }
  } 
}

