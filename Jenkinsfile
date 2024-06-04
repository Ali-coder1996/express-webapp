pipeline {
  agent {
      kubernetes {
          inheritFrom 'jenkins-jenkins-agent maven'
      }
  }
  stages {
    stage('Test') {
      steps {
          sh '''
          echo Hello
          '''
      }
    }
  } 
}

