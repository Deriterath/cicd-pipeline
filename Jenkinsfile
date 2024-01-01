pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        script {
          checkout scm
          def customImage = docker.build("${registry}:${env.BUILD_ID}").inside{

            c-> sh 'scripts/build.sh'}
          }

        }
      }

    }
    environment {
      registry = 'deriterath/practice_task'
    }
  }