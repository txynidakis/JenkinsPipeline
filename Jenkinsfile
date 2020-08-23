pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'The .Net Core Application'
          }
        }

        stage('Test') {
          steps {
            echo 'Testing the Build'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying application'
      }
    }

  }
}