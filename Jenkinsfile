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
      parallel {
        stage('build') {
          steps {
            sh 'dotnet msbuild'
          }
        }
        stage('publish') {
          steps {
            sh 'dotnet publish'
          }
        }
      }
    }
    stage('store') {
      steps {
        sh 'dotnet add package Microsoft.NET.Test.Sdk --version 15.7.0'
        sh 'dotnet test'
      }
    }
    stage('') {
      steps {
        sh 'dotnet store'
      }
    }
  }
}