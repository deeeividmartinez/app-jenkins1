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
        sh 'docker run -d -p 80:80 --rm --name app app:test'
        sh 'nc -vz localhost 80'
        sh 'docker stop app'
      }
    }
    stage('Push Registry') {
      steps {
        echo 'DEPLOY'
        withDockerRegistry([credentialsId: 'DockerHub']) {
          sh 'docker tag app:test deeeividmartinez/app:stable'
          sh 'docker push deeeividmartinez/app:stable'
        }

      }
    }
  }
}