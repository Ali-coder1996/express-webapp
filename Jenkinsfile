pipeline {
  agent {
    kubernetes {
        inheritFrom 'ali'
      }
  }
  stages {
    stage('Environment') {
      steps {
          sh "hostname"
      }
    }
  } 
}