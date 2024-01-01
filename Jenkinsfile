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

      stage('Test') {
        steps {
          script {
            docker.image("${registry}:${env.BUILD_ID}").inside{

              c-> sh 'scripts/test.sh'}
            }

          }
        }

      }
      environment {
        registry = 'deriterath/practice_task'
      }
    }