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
        }
      }
    }
  }
}
