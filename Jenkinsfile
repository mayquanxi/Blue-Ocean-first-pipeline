pipeline {
  agent {
    docker {
      image 'node:13'
      args '-p 3000:3000'
      label 'host'
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
        echo 'you can access website apps: http://127.0.0.1:3000'
        input (
          message: 'Click process for continue or abort to quite pipeline',
          submitter: 'user01, user02, mayquanxi',  //submitter for user01,user02, mayquanxi and admin have permission for aproves jobs
          submitterParameter: 'user_approves'
        ) 
      }
    }

  }
}