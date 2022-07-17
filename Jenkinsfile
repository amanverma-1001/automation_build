pipeline {
  agent none
  stages {
    stage('Node Install') {
      agent {
        docker {
          image 'node:16-alpine'
        }
      }
      
    }
    stage('Docker Build') {
      agent any
      steps {
        sh 'docker-compose up'
      }
    }
  }
}