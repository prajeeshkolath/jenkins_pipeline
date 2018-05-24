pipeline {
  agent any
  tools {
    nodejs 'v6.11.4'
  }
  stages {
    stage('install') {
      steps {
        sh '''
        node -v
        npm -v
        npm install
        '''
      }
    }
    stage('Static Analysis Test') {
      steps {
        sh 'npm run lint'
      }
    }
    stage('Test') {
      steps {
        sh 'npm test'
      }
    }
  }
  post { 
    always { 
      echo 'always run'
    }
    changed { 
      echo 'changed run'
    }
    failure { 
      echo 'failure run'
    }
    success { 
      echo 'success run'
    }
    unstable { 
      echo 'unstable run'
    }
    aborted { 
      echo 'aborted run'
    }
  }
}
