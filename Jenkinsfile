pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Build') {
            steps {
              sh 'docker build -t tmangowal/jc-ah-pipeline .'
            }
        }
        stage('Deliver') {
          steps {
            sh 'docker run --name jc-pipeline-container -p 2021:2021 tmangowal/jc-ah-pipeline &'
          }
        }
    }
}
