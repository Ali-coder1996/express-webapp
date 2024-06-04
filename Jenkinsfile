pipeline {
  agent {
    label 'maven'
  }
  stages {
    stage('Environment') {
      steps {
          sh "terraform --version"
      }
    }
  } 
}