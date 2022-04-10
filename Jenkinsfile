pipeline {
  agent {
    node {
      label 'pipeline'
    }

  }
  stages {
    stage('git') {
      parallel {
        stage('code ') {
          steps {
            git(url: 'https://github.com/TestLeafInc/WebApp.git', branch: 'master')
          }
        }

        stage('stop') {
          steps {
            bat 'stopApp.bat'
          }
        }

        stage('maven') {
          steps {
            bat 'mvn install'
          }
        }

        stage('start') {
          steps {
            bat 'startApp.bat'
          }
        }

      }
    }

  }
}