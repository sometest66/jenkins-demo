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
            sh '''scp -v -i $SSH_KEY /var/jenkins_home/workspace/ssh-test-two/index.js -p 3022 13044-605@45.115.217.93:/root/app/'''
          }
        }
        sh "pwd"
      }
    }
  }
}
