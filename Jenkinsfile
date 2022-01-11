#!/usr/bin/env groovy

pipeline {

    agent { dockerfile true }
    options {
        timeout(time: 5, unit: 'MINUTES')
        buildDiscarder(logRotator(numToKeepStr: "10"))
        timestamps()
    }
    environment {
      HOME = '.'
      SERVICE_NAME = 'report-service'
    }

    stages {

      stage('Cleanup') {
          steps {
              sh 'git clean -fxd'
          }
      }

      stage('yarn install') {
          steps{
              sh 'echo "Please enter build command here"'
          }
      }

      stage('Deploy to DEV') {
          when { branch 'test' }
          steps {
              sh 'echo "deployment steps specific with branch"'

          }
      }

    }

}
