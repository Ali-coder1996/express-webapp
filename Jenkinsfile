pipeline {
  agent {
    kubernetes {
      inheritFrom 'docker'
    }
  }
  stages {
    stage('Environment') {
      steps {
          sh "docker -v"
      }
    }
  } 
}
