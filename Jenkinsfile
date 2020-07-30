pipeline {
  agent any
  tools {nodejs "latest"}
  stages {
    stage('preflight') {
      steps {
        echo sh(returnStdout: true, script: 'env')
        sh 'node -v'
      }
    }
    stage('build') {
      steps {
        sh 'npm --version'
        sh 'git log --reverse -1'
        sh 'npm install'
        sh 'npm install chromedriver --chromedriver_version=LATEST'
        sh 'npm install selenium-cucumber-js --save-dev --force'
      }
    }
    stage('test') {
      steps {
        sh 'npm test'
      }
    }
    stage('deploy') {
        steps {
            sh  'echo Deploying ***'
        }
    }
  }
}