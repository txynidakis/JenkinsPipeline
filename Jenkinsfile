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

        stage('Test Log') {
          steps {
            writeFile(file: 'LogTestFile.txt', text: "This is an automation file log ${ChroneDriverPath}")
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            input(message: 'Do you want to deploy', id: 'OK')
            echo 'Deploying application'
          }
        }

        stage('Artifacts') {
          steps {
            archiveArtifacts 'LogTestFile.txt'
          }
        }

      }
    }

  }
  environment {
    ChroneDriverPath = '/opt/chrome'
  }
}