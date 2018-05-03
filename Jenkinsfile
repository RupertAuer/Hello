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
      }
    }
    stage('build') {
      steps {
        sh 'dotnet msbuild'
      }
    }
    stage('test') {
      steps {
        sh 'dotnet add package Microsoft.NET.Test.Sdk --version 15.7.0'
        sh 'dotnet test /main'
      }
    }
    stage('error') {
      steps {
        sh 'dotnet store'
      }
    }
  }
}