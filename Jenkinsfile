pipeline {
  agent any
  stages {
    stage('Fetch') {
      steps {
        echo 'Fetched the code from GitHub Repo...'
      }
    }
    stage('Continuous Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building....'
          }
        }
        stage('Compile') {
          steps {
            bat 'javac HelloWorld.java'
          }
        }
        stage('Status') {
          steps {
            echo 'Compiled successfully...'
          }
        }
      }
    }
    stage('Continuous Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deploying to server...'
          }
        }
        stage('Execute') {
          steps {
            bat 'java HelloWorld'
          }
        }
      }
    }
    stage('Monitor') {
      steps {
        echo 'Publishing Reports'
      }
    }
  }
}