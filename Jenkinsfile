pipeline {
    agent {
      kubernetes {
        cloud 'kubernetes'
        label 'jenkins'
        defaultContainer 'docker'
        yaml '''
          apiVersion: v1
          kind: Pod
          spec:
            containers:
            - name: docker
              image: docker:24.0.7
              command:
              - cat
              tty: true
              volumeMounts:
                - mountPath: /var/run/docker.sock
                  name: docker-sock
            volumes:
            - name: docker-sock
              hostPath:
                path: /var/run/docker.sock    
          '''
      }
    }

    environment {
      registryCredential = 'reg-logins'
      registry_dev = "alialhjouj/" + "$env.JOB_NAME"

    }

    stages {
      stage('Build/Push Image') {
       steps{
        container('docker') {
        script {
         def version = readFile('VERSION')
         patch = version.trim()
         patch = patch + ".$BUILD_NUMBER"
         
         dockerImage = docker.build registry_dev + ":$patch" , "."
         docker.withRegistry( 'https://index.docker.io/v1/', 'reg-logins' ) { 
                      dockerImage.push(patch)
                 }
         }
        }
      }
       }

    stage('Hello world') {
      agent {
        kubernetes {
          inheritFrom 'jenkins-slave'
        }
      }
      steps {
          sh "kubectl get ns"
      }
    }
      }
}
