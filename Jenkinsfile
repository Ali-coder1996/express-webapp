pipeline {
  agent {
      kubernetes {
          inheritFrom 'jenkins/jenkins-jenkins-agent'
      }
  }
  stages {
    stage('Test') {
      steps {
          echo "PATH = ${PATH}"
      }
    }
  } 
}
