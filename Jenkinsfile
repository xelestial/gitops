pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/xelestial/gitops.git will replace by sed command before RUN
        git url: 'https://github.com/xelestial/gitops.git', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}