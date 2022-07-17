pipeline {
  agent none
  stages{
    stage('Docker Build') {
      agent any
      steps {
        sh 'docker build -t aman1007/jenkinscheck .'
      }
    }
  }
}