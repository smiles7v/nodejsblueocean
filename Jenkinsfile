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
        sh '''chmod +x ./jenkins/scripts/deliver.sh
chmod +x ./jenkins/scripts/kill.sh'''
        sh './jenkins/scripts/deliver.sh'
        input(message: 'Are you finish with website using? (click "proceed" to continue)")', ok: 'Proceed')
        sh './jenkins/scripts/kill.sh'
      }
    }
  }
  environment {
    CI = 'true'
  }
}