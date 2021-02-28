pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Jenkins mini pipeline'
      }
    }
      stage('Checkout') {
      steps {
        git url: 'git@github.com:arunsaxena01/DevOps-Demo-WebApp.git'
      }
    }

  }
}
