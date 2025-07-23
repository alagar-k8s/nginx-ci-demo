pipeline {
  agent any

  stages {
    stage('Clone') {
      steps {
        git 'https://github.com/alagar-k8s/nginx-ci-demo.git'
      }
    }

    stage('Deploy to Minikube') {
      steps {
        sh 'kubectl apply -f nginx-deployment.yaml'
        sh 'kubectl apply -f service.yaml'
      }
    }

    stage('Verify') {
      steps {
        sh 'kubectl get pods'
      }
    }
  }
}
