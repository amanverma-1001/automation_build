pipeline {
  agent none
  stages {
    stage('Maven Install') {
      agent {
        docker {
          image 'node:16-alpine'
        }
      }
      steps {
        sh 'mvn clean install'
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