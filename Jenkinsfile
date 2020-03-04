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

  }
}