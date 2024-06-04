pipeline {
  agent {
      kubernetes {
          inheritFrom 'maven kjkjnkjn'
      }
  }
  stages {
    stage('Environment') {
      steps {
          echo "PATH = ${PATH}"
      }
    }
  } 
}