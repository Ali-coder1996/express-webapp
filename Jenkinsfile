pipeline {
  agent none
  
  stages {
    stage('docker') {
      agent {
        kubernetes {
          inheritFrom 'docker'
        }
      }
      steps {
          sh "docker -v"
      }
    }

    stage('terrafrom') {
      agent {
        kubernetes {
          inheritFrom 'terraform'
        }
      }
      steps {
          sh "terraform --version"
      }
    }
  } 
}
