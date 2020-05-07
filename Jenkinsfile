pipeline {
  agent {
    docker {
      image 'node:13'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('Build') {
      steps {
        echo 'check node version'
        sh 'node --version'
      }
    }

  }
}