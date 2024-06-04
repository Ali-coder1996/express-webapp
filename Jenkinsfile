pipeline {
  agent {
    kubernetes {
      inheritFrom 'jenkins-terraform'
    }
  }
  stages {
    stage('Environment') {
      steps {
          sh "terraform --version"
      }
    }
  } 
}
