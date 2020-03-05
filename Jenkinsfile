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

    stage('Login to dockerhub') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'docker-hub', usernameVariable: 'dockerhubuser', passwordVariable: 'dockerhubpwd')]) {
          sh 'docker login -u ${dockerhubuser} -p ${dockerhubpwd}'
        }
      }
    }

  }
}
