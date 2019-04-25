pipeline {
  agent { label 'nodejs-app' }
  options { 
    buildDiscarder(logRotator(numToKeepStr: '2'))
    skipDefaultCheckout true
  }

  stages {
    stage('Say Hello') {
      steps {
        echo 'Hello World!'   
        sh 'java -version'
      }
    }

  stage('Test') {
      agent { label 'nodejs-app' }
      steps {
        checkout scm
        container('nodejs') {
          echo 'Hello World!'   
          sh 'node --version'
        }
      }
    }


  }
}
