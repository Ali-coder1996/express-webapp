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
          sh "docker version"
          sh "slepp 1000"
      }
    }
  } 
}

