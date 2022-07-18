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
        agent docker
        steps{
            sh 'docker login -u iamapikey -p BfYBYe69roHDLL3ZsQ2DM7FL42wMQdvx9yJhnVZxi-j5 ttp://us.icr.io'
        }
    }
    stage('Docker tag')
    {
        agent docker
        steps{
            sh 'docker tag aman1007/react:5.0 http://us.icr.io/wmldeveloperregistry/amanimage:0.21'
        }
    }
    stage('Docker push')
    {
        agent docker
        steps{
       sh 'docker push http://us.icr.io/wmldeveloperregistry/amanimage:0.21'
        }
    }
 }
}