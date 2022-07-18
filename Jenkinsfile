pipeline {
  agent none
  stages{
    stage('Docker Build') {
      agent any
      steps {
        sh 'docker build -t aman1007/react:5.0 .'
      }
    }
    stage('Docker login')
    {
        agent any
        steps{
            sh 'docker login'
        }
    }
    stage('Docker tag')
    {
        agent any
        steps{
            sh 'docker tag aman1007/react:5.0'
        }
    }
    stage('Docker push')
    {
        agent any
        steps{
       sh 'docker push '
        }
    }
 }
}
