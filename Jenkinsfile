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
        echo 'install npm'
        sh 'npm install'
      }
    }

    stage('Test') {
      steps {
        echo 'Test expose web html'
        sh 'node ./app.js  & sleep 10'
        echo 'you can access website apps'
        input message: 'Click process for continue or abort to quite pipeline', submitter: 'user01, user02, mayquanxi', submitterParameter: 'user_approves'
      }
    }

  }
}