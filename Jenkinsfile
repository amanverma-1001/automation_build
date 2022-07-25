pipeline {
  agent any
  stages{
    stage('Docker Build') {
      steps {
        sh 'docker build -t aman1007/react:5.0 .'
      }
    }
    stage('Docker login')
    {
        steps{
             sh 'docker login -u iamapikey -p BfYBYe69roHDLL3ZsQ2DM7FL42wMQdvx9yJhnVZxi-j5 us.icr.io'
             sh 'docker tag aman1007/react:5.0 us.icr.io/wmldeveloperregistry/amanimage:0.21'
             sh 'docker push us.icr.io/wmldeveloperregistry/amanimage:0.21'
        }
      }
    stage('Install oc'){
                steps{
                    sh 'wget -q https://mirror.openshift.com/pub/openshift-v4/clients/ocp/stable-4.6/openshift-client-linux.tar.gz'
                    sh 'tar xzvf openshift-client-linux.tar.gz --wildcards "oc"'
                    sh 'sudo mv -f oc /usr/local/bin/oc'
                    sh 'oc version'
                    }
            }
    stage('Cluster login') {
            steps {
               sh 'oc login https://api.foramanverma.cp.fyre.ibm.com:6443 -u kubeadmin -p IAK7b-Ea7MB-RUGPn-MWcqI --insecure-skip-tls-verify=true'
               sh 'oc project default'
               sh 'oc apply -f react-deployment.yaml'
              }
         }
   }
}



