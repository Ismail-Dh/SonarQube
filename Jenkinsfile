pipeline {
  agent any
  environment {
    JAVA_HOME = 'C:\\Program Files\\Java\\jdk-21'
    PATH = "${env.JAVA_HOME}\\bin;${env.PATH}"
  }
  stages {
    stage('Analyse Sonar') {
      steps {
        script {
          withSonarQubeEnv('SonarQube') {
            bat 'mvnw.cmd clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'
          }
        }
      }
    }
  }
}
