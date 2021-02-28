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
        git(url: 'git@github.com:arunsaxena01/DevOps-Demo-WebApp.git', branch: 'master', credentialsId: '7e7013a866dd4cc5bc71f34a573cdd58a44a29f4')
      }
    }

    stage('Static Code Analysis') {
      steps {
        withSonarQubeEnv(credentialsId: 'akssonartoken', installationName: 'sonarqube') {
          sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/Maven/bin/mvn -Dsonar.test.exclusions=**/test/java/servlet/createpage_junit.java -Dsonar.login=admin -Dsonar.password=sonar -Dsonar.tests=. -Dsonar.inclusions=**/test/java/servlet/createpage_junit.java -Dsonar.sources=. sonar:sonar -Dsonar.host.url=http://52.152.224.93:9000'
        }

      }
    }

  }
}