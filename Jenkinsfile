pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        git(url: 'https://github.com/tetradev01/nodejsblueocean.git', branch: 'master', poll: true)
        sh 'npm install'
      }
    }
    stage('Test') {
      steps {
        sh 'chmod +x ./jenkins/scripts/test.sh'
        sh './jenkins/scripts/test.sh'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo Deploy'
      }
    }
  }
  environment {
    CI = 'true'
  }
}