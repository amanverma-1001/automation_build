pipeline {
  agent none
  stages{
    stage('Docker Build') {
      agent any
      steps {
        sh 'docker build -t aman1007/react:4.0 .'
      }
    }
    stage('Docker Push') {
      agent any
      steps {
        withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'dockerhubPassword', usernameVariable: 'dockerhubUser')]) {
          sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
          sh 'docker push aman1007/react:4.0'
        }
      }
    }


  }
}