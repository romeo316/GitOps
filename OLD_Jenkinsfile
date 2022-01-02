pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        git url: 'https://github.com/romeo316/GitOps.git', branch: 'main'
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
