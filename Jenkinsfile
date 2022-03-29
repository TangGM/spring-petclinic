pipeline {
  agent any
  stages {
    stage('analyze') {
      steps {
        withSonarQubeEnv(credentialsId: 'sonarqube', installationName: 'sonarqube') {
          sh 'mvn clean verify sonar:sonar -Dsonar.host.url=http://127.0.0.1:9000'
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