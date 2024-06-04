pipeline {
  agent {
    kubernetes {
      inheritFrom 'python'
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
