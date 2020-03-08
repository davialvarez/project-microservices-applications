pipeline {
  agent any
  stages {
    stage('Lint HTML') {
      steps {
        sh '''pwd
ls -lh'''
        sh 'tidy -q -e flask_app/index.html'
      }
    }

    stage('Lint Dockerfile') {
      steps {
        sh 'hadolint Dockerfile'
      }
    }

    stage('Build image') {
      steps {
        sh '''docker build -t dalvaz/swaggerapi .
docker image ls'''
      }
    }

    stage('Push Docker Hub') {
      steps {
        withCredentials(bindings: [usernamePassword(credentialsId: 'docker-hub', usernameVariable: 'dockerhubuser', passwordVariable: 'dockerhubpwd')]) {
          sh '''docker login -u ${dockerhubuser} -p ${dockerhubpwd}
docker tag dalvaz/swaggerapi dalvaz/swaggerapi:1.0
docker push dalvaz/swaggerapi:1.0'''
        }

      }
    }

    stage('Deploy to Kubernetes')  {
      steps {
        withAWS(region: 'us-west-2', credentials: 'aws-credential') {
          sh 'echo "Actualizando Kubeconfig"'
          sh 'aws eks update-kubeconfig --name Cluster-Capstone-eks'
	  sh 'kubectl get node'
        }
      }
    }


  }
}
