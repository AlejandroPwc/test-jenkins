pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        parallel(
          "sonar-test": {
            waitForQualityGate()
            
          },
          "Send to slack": {
            slackSend 'Getting ready'
            
          }
        )
      }
    }
  }
  environment {
    PASSWORD = 'superstrongpassword'
  }
}