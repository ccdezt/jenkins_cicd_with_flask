pipeline {
  // agent { docker { image 'python:3.7.2'} }
  agent any
  stages {
    stage('build') {
      steps {
          sh 'pip install -r requirements.txt --no-cache'
      }
    }
    stage('test') {
      steps {
        sh 'python test.py'
      }
      post {
        always {
            junit 'test-reports/*.xml'
        }
      }
    }
  }
}
