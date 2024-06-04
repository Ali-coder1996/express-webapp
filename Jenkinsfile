pipeline {
  agent {
    label 'terraform'
  }
  stages {
    stage('Environment') {
      steps {
          sh "terraform --version"
      }
    }
  } 
}