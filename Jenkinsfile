pipeline {
  agent any
  stages {
    stage('Bulid') {
      steps {
        sh 'docker run hello-world'
      }
    }
    stage('Test') {
      steps {
        echo 'TEST'
      }
    }
    stage('Deploy') {
      steps {
        echo 'DEPLOY'
      }
    }
  }
}