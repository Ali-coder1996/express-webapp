pipeline {
  agent {
      kubernetes {
          inheritFrom 'jenkins/jenkins-jenkins-agent'
      }
  }
  stages {
    stage('Test') {
      steps {
          sh '''
          terrafrom
          docker -v
          '''
      }
    }
  } 
}
