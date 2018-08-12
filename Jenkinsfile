pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }
    stage('Test') {
      steps {
        sh 'echo Testing'
        sh './jenkins/scripts/test.sh'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo Deploy'
      }
    }
  }
}