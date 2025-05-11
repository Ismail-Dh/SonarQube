pipeline {
  agent any
  environment {
    JAVA_HOME = 'C:\\Program Files\\Java\\jdk-11'
    PATH = "${env.JAVA_HOME}\\bin;${env.PATH}"
  }
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Scan') {
      steps {
        script {
          withSonarQubeEnv(installationName: 'SonarQube') {
            bat 'mvnw.cmd clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'
          }
        }
      }
    }
  }
}
