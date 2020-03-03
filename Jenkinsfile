pipeline {
  agent any
  stages {
    stage('Lint HTML') {
      steps {
        sh '''pwd
ls -lh'''
        sh '''tidy -q -e *.html
ls -lh'''
      }
    }

  }
}
