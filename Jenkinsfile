pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        script {
          checkout scm
          def customImage = docker.build("${registry}:${env.BUILD_ID}").inside{

          c-> sh 'bash build.sh'}
        }

      }
    }

    stage('Test') {
      steps {
        script {
          docker.image("${registry}:${env.BUILD_ID}").inside{

            c-> sh 'bash test.sh'}
          }

        }
      }

    }
    environment {
      registry = 'deriterath/practice_task'
    }
  }
