pipeline {
  agent any
  tools {nodejs "nodejs"}
  stages {
    stage('build') {
      steps {
        sh 'chmod +x ./scripts/build.sh'
        sh 'bash ./scripts/build.sh'
      }
    }

    stage('Test') {
      steps {
        sh 'chmod +x ./scripts/test.sh'
        sh 'bash ./scripts/test.sh'
      }
    }

  }
}
