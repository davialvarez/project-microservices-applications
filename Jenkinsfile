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

    stage('Lint Python app') {
      steps {
        sh './scripts/lint.sh'
      }
    }

    stage('Lint Dockerfile') {
      steps {
        sh 'hadolint Dockerfile'
      }
    }

  }
}