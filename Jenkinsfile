pipeline {
  agent any
  stages {
    stage('Check Code') {
      steps {
        git(url: 'https://github.com/Codehunter-py/curriculum-app-jenkins-pipeline', branch: 'dev')
      }
    }

    stage('Log') {
      parallel {
        stage('Log') {
          steps {
            sh 'ls -la'
          }
        }

        stage('Front-End Unit Tests') {
          steps {
            sh 'cd curriculum-front && npm i'
          }
        }

      }
    }

    stage('Build ') {
      steps {
        sh 'docker build -f curriculum-front/Dockerfile . -t test/curriculum-front:latest'
      }
    }

  }
}