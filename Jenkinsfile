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
            sh '''scp -P 3022 -i $SSH_KEY -v /var/jenkins_home/workspace/ssh-test-two/index.js  13044-605@gate.yetiapp.cloud:/root/app/'''
          }
        }
        sh "pwd"
      }
    }
  }
}
