pipeline {
    agent any
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm --version'
                sh 'git log --reverse -1'
                sh 'npm install'
                sh 'npm install chromedriver --chromedriver_version=LATEST'
                sh 'npm install selenium-cucumber-js --save-dev --force'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying App .. .. ..' 
            }
        }
    }
}