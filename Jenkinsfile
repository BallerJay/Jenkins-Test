pipeline {
  agent any
  stages {
    stage('install-dep') {
      steps {
        git credentialsId: 'b0fad643-2ccd-4898-a09c-f7fd5bac521a', url: 'https://github.com/BallerJay/Jenkins-Test.git'
        sh 'echo \'Hello\''
      }
    }
  }
  post {
  always {
    emailext attachLog: true, body: '''<html>
                <h1>Total cases: ${TEST_COUNTS,var="total"}</h1>
                <h1>pass cases:${TEST_COUNTS,var="pass"}</h1>
                <h1>fail cases:${TEST_COUNTS,var="fail"}</h1>
                </html>''', 
                subject: 'pipeline-notify', 
                to: 'i@ballerjay.me'
    }
  }
}