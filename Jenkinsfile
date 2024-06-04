pipeline {
  agent {
    label 'jenkins/jenkins-jenkins-agent'
  }
  stages {
    stage('Environment') {
      steps {
          sh "terraform --version"
      }
    }
  } 
}