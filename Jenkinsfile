pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'scripts/build.sh'
      }
    }

    stage('Test') {
      steps {
        sh 'scripts/test.sh'
      }
    }

  }
  environment {
    registry = 'deriterath/practice_task'
  }
}