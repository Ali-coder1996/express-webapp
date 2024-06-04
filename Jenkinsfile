pipeline {
  agent {
      kubernetes {
          inheritFrom 'default'
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

