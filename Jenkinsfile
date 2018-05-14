pipeline {
  agent any
  stages {
    stage('Bulid') {
      steps {
        sh 'docker build --tag APP .'
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