pipeline {
    agent {
        node {
            label 'maven'
        }
    }
environment{
    PATH = "/opt/apache-maven-3.9.8/bin:$PATH"
}
    stages {
        stage('build') {
            steps {
                sh 'mvn clean deploy'
            }
        }
    }

    stage('SonarQube analysis') {
    withSonarQubeEnv(credentialsId: '2e32404d87a18e11848c8f6960b6484635f1628e', installationName: '<sonarqubeInstallation>') { // You can override the credential to be used, If you have configured more than one global server connection, you can specify the corresponding SonarQube installation name configured in Jenkins
      sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.11.0.3922:sonar'
    }



}