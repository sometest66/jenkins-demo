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
            script {
              sshCommand remote: '13044-605@gate.yetiapp.cloud', port: 3022, command: 'pwd', key: "$SSH_KEY"
            }
          }
        }
        sh "pwd"
      }
    }
  }
}
