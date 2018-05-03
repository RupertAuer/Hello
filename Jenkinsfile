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
    stage('test') {
      steps {
        sh 'dotnet test'
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
        sh 'dotnet store'
      }
    }
  }
}