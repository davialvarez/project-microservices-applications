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

    stage('Lint Python app') {
      steps {
        sh '''python3 -m venv .lint
source .lint/bin/activate'''
      }
    }

  }
}