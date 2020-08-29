pipeline {
  agent {
    label 'master'
    }

  }
  stages {
    stage('Build') {
      steps {
        nodejs('node') {
          echo 'check node version'
          sh 'node --version'
          echo 'install npm'
          sh 'npm install'
        }
      }
    }

    stage('Test') {
      steps {
        nodejs('node') {
          echo 'Test expose web html'
          sh 'node ./app.js  & sleep 10'
        }
        echo 'you can access website apps: http://127.0.0.1:3000'
        input (
          message: 'Click process for continue or abort to quite pipeline',
          submitter: 'user01, user02, mayquanxi',  //submitter for user01,user02, mayquanxi and admin have permission for aproves jobs  #need use role-base to set permission for job first
          submitterParameter: 'user_approves'
        ) 
      }
    }

  }
}