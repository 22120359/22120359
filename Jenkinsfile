pipeline{
  agent any

  stages {
    stage('Git'){
      steps{
        git branch: 'main', url: 'https://github.com/22120359/22120359.git'
      }
    }

    stage('Build and Push Docker Image'){
      steps{
        withDockerRegistry(credentialsId: 'dockerhub', url: 'https://index.docker.io/v1/') {
          sh 'docker build -t 22120359/mmtnc3:myapp .'
          sh 'docker push 22120359/mmtnc3:myapp'
        }
      }
    }
  }
}