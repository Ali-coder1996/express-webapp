pipeline {
  agent {
    label 'python'
  }
  stages {
    stage('Environment') {
      steps {
          sh "terraform --version"
      }
    }
  } 
}