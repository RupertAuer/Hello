pipeline {
  agent {
    docker {
      image 'microsoft/dotnet'
    }

  }
  stages {
    stage('error') {
      steps {
        sh 'dotnet new console'
        sh 'dotnet run'
      }
    }
    stage('publish') {
      steps {
        sh 'dotnet publish'
      }
    }
  }
}