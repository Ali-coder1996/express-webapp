pipeline {
  agent {
      kubernetes {
          inheritFrom 'maven'
      }
  }
  stages {
    stage('Test') {
      steps {
          sh '''
          terrafrom --version
          '''
      }
    }
  } 
}

