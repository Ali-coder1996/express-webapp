pipeline {
  agent {
      kubernetes {
          yaml """
            apiVersion: v1
            kind: Pod
            spec:
              containers:
              - name: my-container
                image: alialhjouj/jenkins:v1
                tty: true
            """

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