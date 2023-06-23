pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        echo 'hello'
        nodejs('node-18.16.1') {
          sh "node -v"
          sh "node index.js"
          sh "pwd"

          withCredentials([sshUserPrivateKey(credentialsId: 'ssh-credential-one', keyFileVariable: 'SSH_KEY')]) {
              sh '''
                  ssh -i $SSH_KEY 13044-605@gate.yetiapp.cloud -p 3022 "echo hello"
              '''
          }
        }
        sh "pwd"
      }
    }
  }
}
