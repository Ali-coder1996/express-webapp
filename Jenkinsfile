pipeline {
  agent {
    kubernetes {
          inheritFrom 'jenkins/jenkins-jenkins-agent'
      }
  }
  stages {
    stage('Environment') {
      steps {
          sh "hostname"
      }
    }
  } 
}