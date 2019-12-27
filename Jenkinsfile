pipeline {
  agent none
  stages {
    stage('SonarQube') {
      steps {
        waitForQualityGate(credentialsId: '02405b9cd420ec889928e3b2c70ea35d19c39964', abortPipeline: true)
      }
    }

    stage('TestResults') {
      steps {
        junit(testResults: '\\target\\surefire-reports\\*.xml', healthScaleFactor: 1)
      }
    }

  }
}