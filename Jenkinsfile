pipeline {
  agent { label 'docker-ssh-slave' }
  stages {
    stage('Test') {
      steps {
        sh 'docker pull node:16-alpine && node --version'
      }
    }
  }
}
