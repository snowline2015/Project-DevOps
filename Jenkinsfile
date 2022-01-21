pipeline {
    agent any
    environment {
     DOCKERHUB_CREDENTIALS = credentials("dockerhub-19127102")
    }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t 19127102/project_devops:latest .'
      }
    }
    stage('Login') {
     steps {
        sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
      }
    }
    stage('Push') {
      steps {
        sh 'docker push 19127102/project_devops:latest'
      }
    }
  }
}