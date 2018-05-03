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
    stage('Run') {
      steps {
        sh 'dotnet run'
      }
    }
    stage('Store') {
      steps {
        sh 'dotnet store'
      }
    }
  }
}