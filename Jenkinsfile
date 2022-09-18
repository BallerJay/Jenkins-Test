pipeline {
  agent any
  stages {
    stage('install-dep') {
      steps {
        sh 'Build Successed'
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