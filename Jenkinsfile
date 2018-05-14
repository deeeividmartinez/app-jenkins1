pipeline {
  agent any
  stages {
    stage('Bulid') {
      steps {
        sh 'docker build -t app:test .'
      }
    }
    stage('Test') {
      steps {
        echo 'TEST'
        sh 'docker run --rm  --name app -id -p 80:80  app:test'
        sh '/bin/nc -vz localhost 80'
      }
      post {
        always {
          sh 'docker container stop app'
        }
      }
    }
    stage('Push Registry') {
      steps {
        echo 'DEPLOY'
        sh 'docker tag app:test deeeividmartinez/app:stable'
        sh 'docker push deeeividmartinez/app:stable'
      }
    }
  }
}