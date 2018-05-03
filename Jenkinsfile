pipeline {
  agent {
    docker {
      image 'microsoft/dotnet'
    }

  }
  stages {
    stage('New') {
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
    stage('build') {
      steps {
        sh 'dotnet msbuild'
      }
    }
  }
}