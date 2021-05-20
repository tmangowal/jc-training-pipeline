pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Build') {
            steps {
              sh 'docker build -t tmangowal/jc-training-pipeline .'
            }
        }
        stage('Deliver') {
          steps {
            sh 'docker container rm --force jc-pipeline-container && docker run --name jc-pipeline-container -p 2021:2021 tmangowal/jc-training-pipeline &'
          }
        }
    }
}
