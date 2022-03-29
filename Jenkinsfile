pipeline {
  agent any
  stages {
    stage('analyze') {
      steps {
        withSonarQubeEnv(credentialsId: 'sonarqube', installationName: 'sonarqube') {
          sh 'mvn clean sonar:sonar'
        }

      }
    }

    stage('build') {
      steps {
        sh 'mvn package'
      }
    }

  }
}