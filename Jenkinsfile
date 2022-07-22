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
            sh 'docker login -u iamapikey -p BfYBYe69roHDLL3ZsQ2DM7FL42wMQdvx9yJhnVZxi-j5 us.icr.io'
             sh 'docker tag aman1007/react:5.0 us.icr.io/wmldeveloperregistry/amanimage:0.21'
             sh 'docker push us.icr.io/wmldeveloperregistry/amanimage:0.21'
        }
       
 
     }
   
 }
}
