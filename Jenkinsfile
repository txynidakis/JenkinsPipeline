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
            echo "Get the driver path ${ChroneDriverPath}"
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        input(message: 'Do you want to deploy', id: 'OK')
        echo 'Deploying application'
      }
    }

  }
  environment {
    ChroneDriverPath = '/opt/chrome'
  }
}