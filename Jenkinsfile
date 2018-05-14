pipeline {
  agent any
  stages {
    stage('Bulid') {
      steps {
        sh 'docker bulid -t app .'
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