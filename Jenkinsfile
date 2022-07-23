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
               sh 'oc new-project user-getting-started2 --display-name="Getting Started with OpenShift2"'
               sh 'oc adm policy add-role-to-user view -z default -'
               sh 'oc new-app quay.io/openshiftroadshow/parksmap:latest --name=parksmap2'
               sh 'oc get service'
               sh 'oc create route edge parksmap2 --service=parksmap2'
               sh 'oc get route'
              }
         }
   }
}
