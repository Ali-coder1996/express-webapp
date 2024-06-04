pipeline {
  agent {
      kubernetes {
          inheritFrom 'default'
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

