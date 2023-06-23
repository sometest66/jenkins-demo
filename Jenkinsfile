pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        echo 'hello'
        node('node-18.16.1') {
          sh node -v
        }
      }
    }
  }
}
